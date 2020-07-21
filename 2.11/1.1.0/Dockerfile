FROM phenompeople/oraclejre:DEC
LABEL maintainer="dec-team@phenompeople.com" \
      version="1.0" \
      project="kafka"
ARG SCALA_VERSION=2.11
ARG KAFKA_VERSION=1.1.0
EXPOSE 9092
RUN useradd kafka -s /bin/false -u 401 && \
    wget -q -O /tmp/kafka.tar.gz https://archive.apache.org/dist/kafka/${KAFKA_VERSION}/kafka_${SCALA_VERSION}-${KAFKA_VERSION}.tgz && \
    tar -xzf /tmp/kafka.tar.gz -C /usr/local && \
    ln -sf /usr/local/kafka_${SCALA_VERSION}-${KAFKA_VERSION} /usr/local/kafka && \
    chown -R kafka:kafka /usr/local/kafka
ENV KAFKA_HOME=/usr/local/kafka
ENV JMX_PORT=9010
EXPOSE 9010
WORKDIR ${KAFKA_HOME}
USER kafka
ENTRYPOINT ["./bin/kafka-server-start.sh", "config/server.properties"]
