# Format contents of JSON file

VSCode doesn't format JSON file if it's too large.

Use python to format JSON file:

```shell
$ python -m json.tool < file.json
```
