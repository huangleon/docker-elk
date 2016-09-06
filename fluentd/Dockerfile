# https://github.com/fluent/fluentd-docker-image
FROM fluent/fluentd:ubuntu-base
MAINTAINER Duy Lam <duylamphuong@gmail.com>

ENV http_proxy="http://16.216.235.20:8080" https_proxy="http://16.216.235.20:8080"
# Allow fluentd to forward to elasticsearch
RUN gem install --no-ri --no-rdoc fluent-plugin-elasticsearch

