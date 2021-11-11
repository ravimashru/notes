# `switchToLatest` operator

`switchToLatest` can be used with publishers that emit publishers.

When the value of the outer publisher changes, the subscription to the old inner publisher is cancelled and a subcription to the new inner publisher is created.

Example: let's say we want to fetch a random number from an API every time a user taps a button.

The following function simulates an API call by adding a 1 second delay and returning a random number between 0 and 100.

```swift
func getRandomNumberFromApi() -> AnyPublisher<Int, Never> {
    Future() { promise in
        DispatchQueue.main.asyncAfter(deadline: .now() + 1, execute: {
            promise(.success(Int.random(in: 0...100)))
        })
    }
    .print("Random Number API")
    .eraseToAnyPublisher()
}
```

Let's create a `PassthroughSubject` to publish an event whenever a user taps on a button.

```swift
let buttonTaps = PassthroughSubject<Void, Never>()
```

We can now use the `map` operator to fetch a random number whenever a user taps on the button.

```swift
buttonTaps.map { _ in getRandomNumberFromApi() }
```

The return type of this publisher is `Publisher<Publisher<Int, Never>, Never>`.

The complete code to print the random number when a user taps the button would be:

```swift
var cancellables = Set<AnyCancellable>();

buttonTaps
    .print("On Button Tap")
    .map { _ in getRandomNumberFromApi() }
    .switchToLatest()
    .sink { print($0) }
    .store(in: &cancellables)
```

Now let us assume the user taps the button. But before the API call is complete, the user taps the button again.

We can simulate this by calling `send()` on `buttonTaps` in quick succession:

```swift
buttonTaps.send()
buttonTaps.send()
```

We expect `buttonTaps` to emit another event before the API call completes and returns a random number.

Here's what the output looks like:

```
On Button Tap: receive subscription: (PassthroughSubject)
On Button Tap: request unlimited
On Button Tap: receive value: (()) // 1
Random Number API: receive subscription: (Future)
Random Number API: request unlimited
On Button Tap: receive value: (()) // 2
Random Number API: receive cancel // 3
Random Number API: receive subscription: (Future)
Random Number API: request unlimited
Random Number API: receive value: (76) // 4
76
Random Number API: receive finished
```

1. The first button tap event is received
2. The second button tap event is received (before the API call has completed)
3. The previous API call (i.e. call to `getRandomNumberFromApi()`) is cancelled and a new subscription is created (next line of output)
4. The API call completes and a random number is returned.

Note: even when the button was tapped twice, only one random number was fetched. The first API call was cancelled as soon as the button was tapped a second time.

