# echo without newline

Use `echo -n`.

Useful when base64 encoding credentials.

```shell
echo -n 'username:password' | base64
```
