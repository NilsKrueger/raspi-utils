FROM alpine:latest
LABEL org.opencontainers.image.authors="koschiwsf@gmail.com"

RUN apk update && apk add murmur \
    && mkdir -p /data \
    && chmod -R a+rw /data

COPY mumble-server.ini /etc/murmur.ini

EXPOSE 64738/udp
EXPOSE 64738/tcp

VOLUME /data

USER murmur
ENV MURMUR_UNAME='murmur' MURMUR_DATABASE='/data/murmur.sqlite'

ENTRYPOINT ["/usr/bin/murmurd","-fg","-ini","/etc/murmur.ini"]
