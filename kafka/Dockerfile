FROM ubuntu:16.04
ENV KAFKA_USER=kafka \
KAFKA_DATA_DIR=/var/lib/kafka/data \
JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64 \
KAFKA_HOME=/opt/kafka \
PATH=$PATH:/opt/kafka/bin
RUN set -x
RUN apt-get update
RUN apt-get install -y openjdk-8-jre-headless wget
RUN wget -q "http://www.apache.org/dist/kafka/$KAFKA_VERSION/$KAFKA_DIST.tgz"
RUN wget -q "http://www.apache.org/dist/kafka/$KAFKA_VERSION/$KAFKA_DIST.tgz.asc"
RUN wget -q "http://kafka.apache.org/KEYS"
RUN export GNUPGHOME="$(mktemp -d)" 
RUN gpg --import KEYS
RUN gpg --batch --verify "$KAFKA_DIST.tgz.asc" "$KAFKA_DIST.tgz"
RUN tar -xzf "$KAFKA_DIST.tgz" -C /opt
RUN rm -r "$GNUPGHOME" "$KAFKA_DIST.tgz" "$KAFKA_DIST.tgz.asc"


ARG KAFKA_VERSION=0.10.2.1
ARG KAFKA_DIST=kafka_2.11-0.10.2.1
