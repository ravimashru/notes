# sed

`sed` is a Linux utility that can be used to manipulate files, one line at a time.

The `sed` "execution cycle" consists of:
 1. Read a line from `stdin` or the file
 2. Remove trailing new line character
 3. Place the line in a **pattern buffer**
 4. Modify the **pattern buffer** according to the specified command
 5. Print the **pattern buffer** to stdout

The **pattern buffer** is a special place in memory that `sed` copies each line of the file to so that it can perform the operations specified on it.

There is another special buffer called the **hold buffer**. This buffer can be used to save the pattern space and then retrieve it later.

No operations can be performed on the **hold buffer**. It is used only to store data. All operations are performed on the **pattern buffer**.

`sed` provides commands that you can use to move or copy the **pattern buffer** into the **hold buffer**, and vice versa:

| Command | Description |
| ------- | -------- |
| h | overwrite the hold buffer with contents of the pattern buffer |
| H | append a new line, and then the contents of the pattern buffer to the existing contents of the hold buffer |
| g | overwrite the pattern buffer with the contents of the hold buffer |
| G | append a new line, and then the contents of the hold buffer to the existing contents of the pattern buffer |
| x | exchange the contents of the hold and pattern buffers |
