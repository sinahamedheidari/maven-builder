FROM debian:buster-slim

ENV DEBIAN_FRONTEND=noninteractive

## To fix dependency issues
RUN mkdir -p /usr/share/man/man1 /usr/share/man/man2

RUN set -ex \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
    ca-certificates \
    apt-transport-https \
    zip \
    curl \
    git \
    lftp \
    openjdk-11-jdk \
    openssh-client \
    && rm -rf /var/lib/{apt,dpkg,cache,log}/ /tmp/* /var/tmp/*

ENV HOME=/root \
    MVN_VERSION=3.6.3

RUN mkdir -p $HOME/.m2/ && \
    curl -sS \
    http://www.mirrorservice.org/sites/ftp.apache.org/maven/maven-3/${MVN_VERSION}/binaries/apache-maven-${MVN_VERSION}-bin.tar.gz \
    -o /tmp/apache-maven-${MVN_VERSION}-bin.tar.gz && \
    tar xvzf /tmp/apache-maven-${MVN_VERSION}-bin.tar.gz -C /tmp && \
    mv /tmp/apache-maven-${MVN_VERSION} /var/local/ && \
    rm -- /tmp/apache-maven-${MVN_VERSION}-bin.tar.gz && \
    ln -s /var/local/apache-maven-${MVN_VERSION}/bin/mvnyjp /usr/local/bin/mvnyjp && \
    ln -s /var/local/apache-maven-${MVN_VERSION}/bin/mvnDebug /usr/local/bin/mvnDebug && \
    ln -s /var/local/apache-maven-${MVN_VERSION}/bin/mvn /usr/local/bin/mvn
