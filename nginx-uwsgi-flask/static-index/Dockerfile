FROM tiangolo/uwsgi-nginx-flask:flask-index
MAINTAINER Binghao Wang <scorpio147wbh@gmail.com>

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y -f \
        sqlite3 libsqlite3-dev && \
    apt-get clean autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/{apt,dpkg,cache,log} && \
    rm -rf /tmp/* /var/tmp/*

RUN pip install requests
