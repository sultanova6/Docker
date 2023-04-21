FROM nginx:latest

COPY ./run.sh /run.sh
COPY ./main.c /main.c
COPY ./nginx.conf /etc/nginx/nginx.conf

RUN \
    apt update && \
    apt install -y spawn-fcgi && \
    apt install -y libfcgi-dev && \
    apt install -y gcc && \
    chmod 777 run.sh

ENTRYPOINT ["/run.sh"]