FROM alpine:3.11.5

ENV NGINX_VERSION 1.16.1-r8

RUN apk add --no-cache --repository http://dl-cdn.alpinelinux.org/alpine/v3.11/main/aarch64/ \
nginx=${NGINX_VERSION} && mkdir -p /run/nginx

EXPOSE 80

#RUN apt-get update && apt-get install -y \
#    nginx \
# && rm -rf /var/lib/apt/lists/*

COPY custom.conf /etc/nginx/conf.d/

COPY . /opt/

CMD ["nginx", "-g", "daemon off;"]

#docker rmi $(docker images -q)