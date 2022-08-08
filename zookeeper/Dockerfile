FROM ubuntu:22.10 AS extractor

RUN apt-get update
RUN apt-get install wget -y

RUN mkdir /kafka
WORKDIR /kafka

RUN wget https://downloads.apache.org/kafka/3.2.1/kafka_2.13-3.2.1.tgz
RUN tar zxvf kafka_2.13-3.2.1.tgz

FROM openjdk:8u342-oracle

EXPOSE 9092

RUN mkdir /kafka
WORKDIR /kafka

COPY --from=extractor /kafka/kafka_2.13-3.2.1/ ./

COPY zookeeper.properties /kafka/config/zookeeper.properties

CMD ["/kafka/bin/zookeeper-server-start.sh", "/kafka/config/zookeeper.properties"]