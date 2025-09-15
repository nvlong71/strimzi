from quay.io/strimzi/kafka:0.44.0-kafka-3.7.0

USER root
RUN mkdir -p /opt/kafka/plugins

ADD ./debezium-connector-mysql/ /opt/kafka/plugins/debezium-connector-mysql/

USER 1001
