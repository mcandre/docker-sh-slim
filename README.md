# docker-sh-slim - a slim Docker container that launches a shell session for running multiple commands

# ABOUT

docker-sh-slim is a container for running interactive shell sessions, made smaller with a few techniques:

* Identify dependencies with [strace](http://sourceforge.net/projects/strace/).
* Switch base image from [ubuntu](https://registry.hub.docker.com/_/ubuntu/) to [scratch](https://docs.docker.com/articles/baseimages/#creating-a-simple-base-image-using-scratch).

# DOCKER HUB

https://registry.hub.docker.com/u/mcandre/docker-sh-slim/

# EXAMPLE

```
$ make
docker run -it mcandre/docker-sh-slim sh
/ # ls /
ls /
bin      etc      lib      linuxrc  mnt      proc     run      sys      usr
dev      home     lib64    media    opt      root     sbin     tmp      var
/ # exit
exit
docker images | grep mcandre/docker-sh-slim | awk '{ print $(NF-1), $NF }'
2.433 MB
```

# REQUIREMENTS

* [Docker](https://www.docker.com/)

## Optional

* [make](http://www.gnu.org/software/make/)

## Debian/Ubuntu

```
$ sudo apt-get install docker.io build-essential
```

## RedHat/Fedora/CentOS

```
$ sudo yum install docker-io
```

## non-Linux

* [VirtualBox](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/)
* [boot2docker](http://boot2docker.io/)

### Mac OS X

* [Xcode](http://itunes.apple.com/us/app/xcode/id497799835?ls=1&mt=12)
* [Homebrew](http://brew.sh/)
* [brew-cask](http://caskroom.io/)

```
$ brew cask install virtualbox vagrant
$ brew install boot2docker
```

### Windows

* [Chocolatey](https://chocolatey.org/)

```
> chocolatey install docker make
```
