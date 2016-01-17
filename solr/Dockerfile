FROM scorpio147wbh/server-jre
MAINTAINER Binghao Wang <scorpio147wbh@gmail.com>

ENV SOLR_VERSION 5.3.1

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y curl && \
    curl -L -O "http://archive.apache.org/dist/lucene/solr/${SOLR_VERSION}/solr-${SOLR_VERSION}.tgz.md5" && \
    curl -L -O "http://archive.apache.org/dist/lucene/solr/${SOLR_VERSION}/solr-${SOLR_VERSION}.tgz" && \
    md5sum -c solr-${SOLR_VERSION}.tgz.md5 && \
    mkdir -p /opt/solr && \
    tar -zxf solr-${SOLR_VERSION}.tgz -C /opt/solr --strip-components=1 && \
    apt-get purge -y curl && \
    apt-get clean autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/{apt,dpkg,cache,log} && \
    rm -rf /tmp/* && \
    rm solr-${SOLR_VERSION}.tgz solr-${SOLR_VERSION}.tgz.md5

EXPOSE 8983

CMD ["/opt/solr/bin/solr", \
    "-f"]
