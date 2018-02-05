# Janus gateway in a Docker Container

[![Build Status](https://travis-ci.org/linagora/docker-janus-gateway.svg?branch=mach10)](https://travis-ci.org/linagora/docker-janus-gateway)

Run janus gateway well configured for Hublin in a Docker container.

## Usage

Assuming Docker and Docker Compose are installed:

Build the image

```shell
$ docker build -t linagora/janus-gateway .
```

Run the container

```shell
$ DOCKER_IP=<THE IP OF YOUR DOCKER> docker run -p 80:80 -p 7088:7088 -p 8088:8088 -p 8188:8188 -p 10000-10200:10000-10200/udp linagora/janus-gateway
```

Where `DOCKER_IP` is the public IP address where Docker services can be reached. This will be used by Janus to send back the right IP to Web clients (ICE candidates) so that they can communicate with Janus correctly.

That's it!

Details:

To make this even easier, copy `docker-compose.yml` [from this repo](https://github.com/linagora/docker-janus-gateway/blob/master/docker-compose.yml). Then you'll only need to:

```shell
$ DOCKER_IP=<YOUR DOCKER IP> docker-compose up
```

Where ports:
  - **80**: expose janus documentation and admin/monitoring website
  - **7088**: expose Admin/monitor server
  - **8088**: expose Janus server
  - **8188**: expose Websocket server
  - **10000-10200/udp**: Used during session establishment

