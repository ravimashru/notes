# Removing Containers

Remove all containers with a specific status (e.g. `exited`):

```shell
$ docker rm $(docker ps -f status=exited -q)
```

Remove all containers:

```shell
docker rm $(docker ps -q)
```
