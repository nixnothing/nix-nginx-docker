cloned from https://github.com/DvdGiessen/nginx-rtmp-docker for personal use

nginx docker image with config for reverse proxy with use with other docker images and fedora packages
original dockerfile was modified to build using fedora and config changes to nginx config with allow more use of other containers via reverse proxy configs

Below is the original readme for the base nginx-rtmp-docker repo highlighting use of the base rtmp server features for nginx

--------

# nginx-rtmp-docker
**Dockerfile for building lightweight nginx + rtmp module for replicating streams**

![docker pulls](https://img.shields.io/docker/pulls/dvdgiessen/nginx-rtmp-docker.svg)
![docker image size](https://img.shields.io/microbadger/image-size/dvdgiessen/nginx-rtmp-docker.svg)

## Usage
### How to run the server
```sh
docker run -dp 1935:1935 dvdgiessen/nginx-rtmp-docker
```

### How to stream to the server
Set OBS up with the following settings:
 * Go to Settings > Stream.
 * Fill out the following settings:
   * Stream Type: Custom Streaming Server.
   * URL: `rtmp://localhost:1935/live`. Replace `localhost` with the IP
     of where the server is running.
   * Stream key: `my-stream-key`. This can be anything you want.

### How to view the stream
Using VLC:
 * Go to Media > Open Network Stream.
 * Enter the following URL: `rtmp://localhost:1935/live/my-stream-key`.
   Replace `localhost` with the IP of where the server is running, and
   `my-stream-key` with the stream key you used when setting up the stream.
 * Click Play.

## More info
Docker Hub: https://hub.docker.com/r/dvdgiessen/nginx-rtmp-docker/
