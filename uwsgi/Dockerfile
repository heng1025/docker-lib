FROM alpine

LABEL maintainer="iron"

EXPOSE 80

WORKDIR /app

COPY ./app.py /app/app.py
COPY ./app.ini /etc/uwsgi/uwsgi.ini


RUN sed -i s/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g /etc/apk/repositories && \
    apk --update add uwsgi-python py3-pip py3-lxml tzdata && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone && apk del tzdata && \ 
    pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/

CMD [ "uwsgi", "/etc/uwsgi/uwsgi.ini" ]