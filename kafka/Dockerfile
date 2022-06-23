FROM ubuntu:16.04
ENV KAFKA_USER=kafka \
KAFKA_DATA_DIR=/var/lib/kafka/data \
JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64 \
KAFKA_HOME=/opt/kafka \
PATH=$PATH:/opt/kafka/bin
RUN set -x
RUN apt-get update
RUN apt-get install -y openjdk-8-jre-headless wget


ARG KAFKA_VERSION=0.10.2.1
ARG KAFKA_DIST=kafka_2.11-0.10.2.1
