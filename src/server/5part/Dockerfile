FROM nginx:latest

COPY ./run.sh /run.sh
COPY ./main.c /main.c
COPY ./nginx.conf /etc/nginx/nginx.conf

RUN \
    chmod 777 usr/bin/passwd && \
    chmod 777 usr/bin/gpasswd && \
    chmod 777 usr/bin/chsh && \
    chmod 777 sbin/unix_chkpwd && \
    chmod 777 usr/bin/newgrp && \
    chmod 777 usr/bin/chage && \
    chmod 777 usr/bin/wall && \
    chmod 777 bin/umount && \
    chmod 777 bin/su && \
    chmod 777 usr/bin/expiry && \
    chmod 777 usr/bin/chfn && \
    chmod 777 bin/mount && \
    apt update && \
    apt install -y spawn-fcgi && \
    apt install -y libfcgi-dev && \
    apt install -y gcc && \
    rm -rf /var/lib/apt/lists && \
    chmod 777 run.sh

USER nginx
HEALTHCHECK NONE
ENTRYPOINT ["/run.sh"]