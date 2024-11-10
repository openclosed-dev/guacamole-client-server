FROM ubuntu:noble

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update

ADD guacd_*.deb /

RUN apt-get install -y /guacd_*.deb \
    && rm -f /guacd_*.deb

ENV LD_LIBRARY_PATH=/opt/guacamole/lib   

ENTRYPOINT ["/opt/guacamole/sbin/guacd", "-b", "0.0.0.0", "-f"]
