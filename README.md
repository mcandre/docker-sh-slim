# docker-sh-slim - a slim Docker container that launches a shell session for running multiple commands

# ABOUT

docker-sh-slim is a container for running interactive shell sessions, made smaller with a few techniques:

* Identify dependencies with [strace](http://sourceforge.net/projects/strace/).
* Switch base image from [ubuntu](https://registry.hub.docker.com/_/ubuntu/) to [busybox](https://registry.hub.docker.com/_/busybox/).

# DOCKER HUB

https://registry.hub.docker.com/u/mcandre/docker-sh-slim/

# EXAMPLE

```
$ make
echo 'exit' | docker run mcandre/docker-sh-slim sh
docker images | grep mcandre/docker-sh-slim | awk '{ print $(NF-1), $NF }'
2.433 MB
```

# REQUIREMENTS

* [Docker](https://www.docker.com/)

## Optional

* [make](http://www.gnu.org/software/make/)
* [Node.js](https://nodejs.org/en/) (for dockerlint)
