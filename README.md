# docker-shadowsocks-libev-client
Build a docker image for shadowsocks-libev client with simple-obfs, based on Alpine Linux.

Server: https://hub.docker.com/r/acrisliu/shadowsocks-libev/

Server Run:
```
docker run -e ENCRYPT_METHOD=chacha20-ietf-poly1305 -e PASSWORD=<your_password> -d --name=shadowsocks-libev -p 3389:8388/tcp -p 3389:8388/udp --restart=always acrisliu/shadowsocks-libev
```

Client Run:
```
docker run -e SERVER_HOST=<remote_ip> -e SERVER_PORT=3389 -e ENCRYPT_METHOD=chacha20-ietf-poly1305 -e PASSWORD=<your_password> -d --name=shadowsocks-libev-client -p 3080:1080/tcp -p 3080:1080/udp --restart=always ninehills/shadowsocks-libev-client
```
