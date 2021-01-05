# Building images using BuildKit

BuildKit is an overhaul of the build architecture. It improves performance, storage management, security, etc.

More information: [Build images with BuildKit - Docker Docs](https://docs.docker.com/develop/develop-images/build_enhancements/)

Easiest way to use BuildKit:

```shell
$ DOCKER_BUILDKIT=1 docker build .
```