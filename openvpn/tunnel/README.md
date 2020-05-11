### 让客户端挂到当前容器环境中可以访问未开放的端口

#### 构建
docker build -t shijian/openvpn-tunle:lts-alpine .

#### 运行
docker run -d -p 1194:1194/udp --cap-add=NET_ADMIN --restart=always -e REMOTE_IP=10.134.44.55 --name openvpn shijian/openvpn-tunle:lts-alpine

#### 初始化客户端
docker exec -it openvpn /bin/sh
  sh /init-client && cat $OPENVPN/$REMOTE_IP.ovpn
