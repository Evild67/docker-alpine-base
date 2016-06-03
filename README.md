[![Docker Stars](https://img.shields.io/docker/stars/evild/alpine-base.svg?style=flat-square)](https://hub.docker.com/r/evild/alpine-base/)
[![Docker Pulls](https://img.shields.io/docker/pulls/evild/alpine-base.svg?style=flat-square)](https://hub.docker.com/r/evild/alpine-base/)
[![ImageLayers Size](https://img.shields.io/imagelayers/image-size/evild/alpine-base/latest.svg?style=flat-square)](https://hub.docker.com/r/evild/alpine-base/)

# Alpine Base

This image is based on [Alpine](https://hub.docker.com/_/alpine/) and includes [s6](https://github.com/just-containers/s6-overlay), to make it easy to start multiple process and manage them correctly.

## Version

- `latest` [(Dockerfile)](https://github.com/Evild67/docker-alpine-base/blob/master/Dockerfile)
- `3.0`[(Dockerfile)](https://github.com/Evild67/docker-alpine-base/blob/3e2a3de6f428f91264d3edff108502c1b960f0f8/Dockerfile) (Alpine 3.4)
- `2.0` [(Dockerfile)](https://github.com/Evild67/docker-alpine-base/blob/10c778432409a0f2b0c02d87de153a693f31aadc/Dockerfile) (Alpine 3.3)


## What is Alpine Linux ?
Alpine Linux is a Linux distribution built around musl libc and BusyBox. The image is only 5 MB in size and has access to a package repository that is much more complete than other BusyBox based images. This makes Alpine Linux a great image base for utilities and even production applications. Read more about Alpine Linux here and you can see how their mantra fits in right at home with Docker images.

## Usage

Include `FROM evild/alpine-base` at the top of your Dockerfile. Starting from `evild/alpine-base` provides you with the ability to easily start any service using s6.

Start service using s6:
* Create a folder at /etc/services.d/service-name
* You need to create a file named `run` in this folder:

```
#!/bin/sh

exec nginx;
```
