FROM ubuntu:14.04
MAINTAINER Binghao Wang <scorpio147wbh@gmail.com>

ENV JAVA_HOME /opt/jdk1.8.0_66

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y curl && \
    echo "073f2bdcb3b993f756772f4225bf05b6006516bf1d7d1672fb2ec2aff4e83736 server-jre-8u66-linux-x64.tar.gz" > SHA256SUM && \
    curl -b oraclelicense=accept-securebackup-cookie -O -L 'http://download.oracle.com/otn-pub/java/jdk/8u66-b17/server-jre-8u66-linux-x64.tar.gz' && \
    sha256sum -c SHA256SUM && \
    mkdir -p /opt && \
    tar -zxf server-jre-8u66-linux-x64.tar.gz -C /opt && \
    update-alternatives --install /usr/bin/java java $JAVA_HOME/bin/java 9999 && \
    apt-get purge -y curl && \
    apt-get clean autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/{apt,dpkg,cache,log} && \
    rm -rf /tmp/* && \
    rm server-jre-8u66-linux-x64.tar.gz SHA256SUM
