FROM ubuntu:noble

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get upgrade -y && apt-get install -y curl

RUN curl -fsSL https://github.com/openclosed-dev/guacamole-server-builder/releases/download/v1.5.5-3/guacd_1.5.5-3noble_amd64.deb -o guacd_1.5.5-3noble_amd64.deb \
    && apt-get install -y /guacd_*.deb \
    && rm -f /guacd_*.deb

USER guacd

ENV LD_LIBRARY_PATH=/opt/guacamole/lib   

ENTRYPOINT ["/opt/guacamole/sbin/guacd", "-b", "0.0.0.0", "-f"]
