# Delete All Local Branches

```shell
$ git branch | grep -v "master" | xargs git branch -D 
```

Source: https://coderwall.com/p/x3jmig/remove-all-your-local-git-branches-but-keep-master