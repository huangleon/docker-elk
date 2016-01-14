# EFK-based logging stack for dockerized applications

*docker-efk* is a Docker Compose service to help you store / query logging messages in your applications. All you have to do is to launch it with `docker-compose` and tell your docker containers to forward log messages to running fluend (by using `--log-driver=fluentd`). That's it

# How it works

1. Look at Docker's [logging driver](https://docs.docker.com/engine/reference/logging/overview/) feature if you feel `docker logs` doesn't suit your need
1. Consult [docker-elk](https://github.com/deviantony/docker-elk) for installing necessary tools
1. Download (or `git clone`) this repository in a server with Docker installed
1. Launch the stack by running `docker-compose up -d`
1. By default, the stack exposes the following ports:
  - 24224: Fluend TCP input
  - 5601: Kibana Website
  - Port 9200, 9300 of ElasticSearch container is mapped to host randomly, you can use `docker inspect` to find out what they're
1. Add option `--log-driver=fluentd` when creating your docker containers (by either `docker run` or `docker create`). See Docker [Fluentd logging driver](https://docs.docker.com/engine/reference/logging/fluentd) for more options e.g. `fluentd-address`
1. Now log messages from your containers should appear in Kibana website