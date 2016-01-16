FROM ubuntu:14.04
MAINTAINER Binghao Wang <scorpio147wbh@gmail.com>

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y -f \
        wget \
        cmake \
        g++ && \
    mkdir -p /opt && \
    wget -q -O - https://github.com/HIT-SCIR/ltp/archive/v3.3.0.tar.gz | tar -zx -C /opt && \
    cd /opt/ltp-3.3.0 && ./configure && make && \
    apt-get purge -y wget cmake g++; \
    apt-get clean autoclean; \
    apt-get autoremove -y; \
    rm -rf /var/lib/{apt,dpkg,cache,log}; \
    rm -rf /tmp/*

EXPOSE 12345

ENTRYPOINT ["/opt/ltp-3.3.0/bin/ltp_server"]
CMD ["--log-level",  "2", \
    "--threads", "1", \
    "--port", "12345", \
    "--last-stage", "all", \
    "--segmentor-model", "/ltp_data/cws.model", \
    "--postagger-model", "/ltp_data/pos.model", \
    "--ner-model", "/ltp_data/ner.model", \
    "--parser-model", "/ltp_data/parser.model", \
    "--srl-data", "/ltp_data/srl/"]
