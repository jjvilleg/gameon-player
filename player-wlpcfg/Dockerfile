FROM gameontext/docker-liberty-custom:master-12

ENV SERVERDIRNAME player

COPY ./startup.sh /opt/startup.sh
COPY ./servers/gameon-player /opt/ol/wlp/usr/servers/defaultServer/
COPY ./lib/features/ /opt/ol/wlp/usr/

COPY ./player.json /opt/player.json

CMD ["/opt/startup.sh"]

HEALTHCHECK \
  --timeout=10s \
  --start-period=40s \
  CMD wget -q -O /dev/null http://localhost:9080/health
