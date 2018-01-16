# Janus gateway in a Docker Container

[![Build Status](https://travis-ci.org/linagora/docker-janus-gateway.svg?branch=mach10)](https://travis-ci.org/linagora/docker-janus-gateway)

Run janus gateway well configured for Hublin in a Docker container.

## Usage
Assuming Docker and Docker Compose are installed:

Build the image
```shell
$ docker build -t linagora/docker-janus-gateway .
```

Run the container
```shell
$ docker run -p 80:80 -p 7088:7088 -p 8088:8088 -p 8188:8188 linagora/docker-janus-gateway
```

That's it!

Details: 

To make this even easier, copy `docker-compose.yml` [from this repo](https://github.com/linagora/docker-janus-gateway/blob/master/docker-compose.yml). Then you'll only need to:

```shell
$ docker-compose up
```

Where port:
  - **80**: expose janus documentation and admin/monitoring website
  - **7088**: expose Admin/monitor server
  - **8088**: expose Janus server
  - **8188**: expose Websocket server
