# 2048

A HashiCorp reskin of [Gabriele Cirulli's version of 2048](https://github.com/gabrielecirulli/2048).

Playable [here](https://tunzor.ca/hashi-2048)

## Screenshot
![2048 screenshot](images/screen-cap.jpg)

## Docker Image

A Docker Image of 2048 can be built with the following `Dockerfile`:

```dockerfile
FROM alpine:latest

MAINTAINER Anthony Russo <github.com/tunzor>

RUN apk --update add nginx

COPY ./2048 /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]  
```

1.) Create a `Dockerfile` in the directory _above_ the clone of this repository.

2.) Build the Docker Image locally using `docker build . --tag "2048"`

3.) Tag the Docker Image using `docker tag 2048 ghcr.io/tunzor/hashi-2048:1.0.0`

4.) Push the Docker Image to [GHCR](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-docker-registry) using `docker push ghcr.io/tunzor/hashi-2048:1.0.0`