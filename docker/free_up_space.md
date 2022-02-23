# Free up space

```shell
$ docker system prune
```

Removes:
- all stopped containers
- all networks not used by at least one container
- all dangling images
- all build cache


```shell
$ docker system prune -a --volumes
```

In addition to above, removes:
- all volumes not used by at least one container
- all images without at least one container associated to them



More: https://docs.docker.com/engine/reference/commandline/system_prune/
