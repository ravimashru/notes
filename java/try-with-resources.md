# Try with Resources

A type of `try` statement that declares the resources that will be used in the scope of the try statement.

After the try statement is executed, the resources are closed and cleaned up automatically.

The declared resources need to implement the `java.lang.AutoCloseable` interface.



*Example of code with a regular `try` statement:*

```java
Reader reader;

try {
	reader = Helper.getReader("file1.txt");
	// Do stuff with reader
} catch (IOException e) {
	// Handle exception
} finally {

	if (reader != null) {
		try {
			reader.close();	
		} catch (IOException e2) {
			// Handle exception
		}
	}
	
}
```



*Example of code using `try with resources`:*

```java
try ( Reader reader = Helper.getReader("file1.txt");
	  Writer writer = Helper.getWriter("file2.txt"); ) {

	// Do stuff with `reader` and `writer`

} catch (IOException e) {
	// Handle exception
}
```

There's no need to call `close()` on the resources explicitly!