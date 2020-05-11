FROM alpine:3.11.5
LABEL maintainer="Shawn Shi<shijianws@163.com>"
ENV SERVER_URL="" OPENVPN="/opt/openvpn"
COPY init-* /
RUN echo -e "https://mirrors.aliyun.com/alpine/v3.11/main\nhttps://mirrors.aliyun.com/alpine/v3.11/community" > /etc/apk/repositories && \
    apk add --no-cache easy-rsa openvpn && \
    rm -rf /var/cache/apk/* /tmp/* /var/tmp/* && \
    sh /init-env && sh /init-pki && sh /init-server && \
    # 启动脚本
    echo -e '#!/bin/sh\nset -eu\nmkdir -p /dev/net\nif [ ! -c /dev/net/tun ]; then\n  mknod /dev/net/tun c 10 200\nfi\n\nopenvpn --config $OPENVPN/openvpn.conf' > docker-entrypoint.sh && chmod +x docker-entryp    echo -e '#!/bi4/udp
ENTRYPOINT [ "/dockENTRYPOINT [ "sh" ]
