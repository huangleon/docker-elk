FROM kibana:latest

ENV http_proxy="http://16.216.235.20:8080" https_proxy="http://16.216.235.20:8080"
RUN apt-get update && apt-get install -y netcat

COPY entrypoint.sh /tmp/entrypoint.sh
RUN chmod +x /tmp/entrypoint.sh

#RUN kibana plugin --install elastic/sense
COPY sense-latest.tar.gz /sense-latest.tar.gz
RUN kibana plugin -i sense -u file:///sense-latest.tar.gz

CMD ["/tmp/entrypoint.sh"]

