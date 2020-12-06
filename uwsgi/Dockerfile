FROM alpine

LABEL maintainer="iron"

RUN sed -i s/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g /etc/apk/repositories && \
    apk --update add uwsgi-python py3-pip py3-lxml tzdata && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone && apk del tzdata && \ 
    pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/