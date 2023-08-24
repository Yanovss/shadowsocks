FROM alpine:3.18.3

ENV SS_SERVER_ADDR=0.0.0.0 \
    SS_SERVER_PORT=8388 \
    SS_PASSWORD=nEydJPp \
    SS_METHOD=chacha20-ietf-poly1305 \
    SS_TIMEOUT=300 \
    SS_LOCAL_PORT=51820 \
    SS_LOCAL_ADDR=0.0.0.0 \
    SS_TUNNEL_ADDR=0.0.0.0:51820

RUN apk add --no-cache --update-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/testing/ --allow-untrusted shadowsocks-libev

EXPOSE ${SS_LOCAL_PORT}/tcp ${SS_LOCAL_PORT}/udp

ENTRYPOINT /usr/bin/ss-tunnel -s ${SS_SERVER_ADDR} -p ${SS_SERVER_PORT} -b ${SS_LOCAL_ADDR} -l ${SS_LOCAL_PORT} -L ${SS_TUNNEL_ADDR} -k ${SS_PASSWORD} -m ${SS_METHOD} -t ${SS_TIMEOUT} -U