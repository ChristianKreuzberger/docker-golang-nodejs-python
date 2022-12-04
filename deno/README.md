# Docker Deno

This provides quick examples and size comparison of a very simple Deno application using express.

## Normal build

```bash
docker build . -t deno-docker-build:latest
```

## Alpine build

```bash
docker build . -f Dockerfile.alpine -t deno-alpine-docker-build:latest
```


## Distroless multistage build

**does not work**
```bash
docker build . -f Dockerfile.distroless -t deno-distroless-docker-build:latest
```

## Compare
```bash
$> docker images | grep deno
deno-distroless-docker-build         latest              97bc7a2aae7a   About a minute ago   140MB
deno-alpine-docker-build             latest              83cf91cd0444   2 hours ago          135MB
deno-docker-build                    latest              4c8ced131565   2 hours ago          198MB
```
