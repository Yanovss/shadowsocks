FROM alpine:3.18.3

ENV SS_SERVER_ADDR=0.0.0.0 \
    SS_SERVER_PORT=8388 \
    SS_PASSWORD=nEydJPp \
    SS_METHOD=chacha20-ietf-poly1305 \
    SS_TIMEOUT=300

RUN apk add --no-cache --update-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/testing/ --allow-untrusted shadowsocks-libev

EXPOSE ${SS_SERVER_PORT}/tcp ${SS_SERVER_PORT}/udp

ENTRYPOINT /usr/bin/ss-server -s ${SS_SERVER_ADDR} -p ${SS_SERVER_PORT} -k ${SS_PASSWORD} -m ${SS_METHOD} -t ${SS_TIMEOUT} -U