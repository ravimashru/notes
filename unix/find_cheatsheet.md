# `find` command cheatsheet

To find all files in the `src` folder that have the text `myFunction`:

```
find src -type f -exec grep 'myFunction' {} -l \;  
```

Note: `-l` is a grep option to print only name of files containing matching lines.

## Resources

- [find command in Linux with examples - Geeksforgeeks](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)
