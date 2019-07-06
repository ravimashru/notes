# Custom Image Generator in Keras

```
def image_generator(x_train, y_train, batch_size=64):
  
  curr_index = 0
  
  while True:
    
    X = x_train[curr_index: curr_index + batch_size]
    Y = y_train[curr_index: curr_index + batch_size]
    
    curr_index += batch_size
    if curr_index > len(x_train):
      curr_index = 0
    
    batch_x = []
    batch_y = []
    
    for (x, y) in zip(X, Y):
      batch_y.append(y)
      
      x_large = cv2.resize(x, (224, 224), interpolation=cv2.INTER_AREA)
      batch_x.append(x_large)
      
    yield (
        np.array(batch_x),
        np.array(batch_y)
    )

new_model.fit_generator(
    image_generator(x_train, y_train),
    steps_per_epoch=50000 / 64, epochs=5
)
```

1. Create a method (e.g. `image_generator`) that takes the entire set of training data as a parameter. The parameters could also be the location of where the images are stored.

1. The method is a generator function that keeps returning a batch of X and Y values. That's why everything is in an infinite loop.

1. Inside the loop, select which images from the training set should be a part of the batch, perform any pre-processing required, and yield a tuple of two numpy arrays - the batches of X and Y data to be fed to the network.