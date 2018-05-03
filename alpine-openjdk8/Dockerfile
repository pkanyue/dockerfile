# docker build -t rlax/alpine-openjdk8 ./
FROM openjdk:8-alpine

MAINTAINER Rlax <rlaxuc@gmail.com>

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories

ARG TZ="Asia/Shanghai"

ENV TZ ${TZ}

RUN apk upgrade --update \
    && apk add bash curl tar wget ca-certificates \
        tzdata unzip font-adobe-100dpi ttf-dejavu \
    && ln -sf /usr/share/zoneinfo/${TZ} /etc/localtime \
    && echo ${TZ} > /etc/timezone \
    && rm -rf /var/cache/apk/*

CMD ["bash"]