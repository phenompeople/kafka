FROM phenompeople/centos-sunjre
MAINTAINER Rajesh Jonnalagadda(<admin.squad@phenompeople.com>)
ARG KAFKA_VERSION=0.11.0.1
EXPOSE 9092
RUN useradd kafka -s /bin/false -u 401 && \
	wget -q -O /tmp/kafka.tar.gz http://www-us.apache.org/dist/kafka/${KAFKA_VERSION}/kafka-${KAFKA_VERSION}-src.tgz && \
	tar -xzf /tmp/kafka.tar.gz -C /opt && \
	ln -sf /opt/kafka-${KAFKA_VERSION}-src /opt/kafka && \
	chown -R kafka:kafka /opt/kafka
ENV KAFKA_HOME=/opt/kafka
WORKDIR ${KAFKA_HOME}
USER kafka
ENTRYPOINT ["./bin/kafka-server-start.sh", "config/server.properties"]