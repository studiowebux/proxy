# Studiowebux Proxy

```bash
docker network create -d bridge proxy
docker compose up -d
```

## Set custom configs per vhost

https://github.com/nginx-proxy/nginx-proxy/tree/main/docs#custom-nginx-configuration

For example, set the body size to 512m for pixel-it:

```bash
docker run --rm -it -v /var/lib/docker/volumes/proxy_vhost/_data:/etc/nginx/vhost.d nginxproxy/nginx-proxy bash

{ echo 'server_tokens off;'; echo 'client_max_body_size 512m;'; } > /etc/nginx/vhost.d/pixel-it.webuxlab.com
```
