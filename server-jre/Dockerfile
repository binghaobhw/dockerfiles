FROM ubuntu:14.04
MAINTAINER Binghao Wang <scorpio147wbh@gmail.com>

ENV JAVA_HOME /opt/jdk1.8.0_66

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y wget && \
    mkdir -p /opt && \
    wget -q -O - --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" \
        "http://download.oracle.com/otn-pub/java/jdk/8u66-b17/server-jre-8u66-linux-x64.tar.gz" | tar -zx -C /opt && \
    update-alternatives --install /usr/bin/java java $JAVA_HOME/bin/java 9999 && \
    apt-get purge -y wget; \
    apt-get clean autoclean; \
    apt-get autoremove -y; \
    rm -rf /var/lib/{apt,dpkg,cache,log}; \
    rm -rf /tmp/*; \
