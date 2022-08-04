FROM openjdk:8u342-oracle

EXPOSE 2181

RUN apt-get update
RUN apt-get install wget -y

RUN mkdir /kafka
WORKDIR /kafka

RUN wget https://downloads.apache.org/kafka/3.2.1/kafka_2.13-3.2.1.tgz

RUN tar zxvf kafka_2.13-3.2.1.tgz

COPY zookeeper.properties /kafka/kafka_2.13-3.2.1/config/zookeeper.properties

CMD ["/kafka/kafka_2.13-3.2.1/bin/zookeeper-server-start.sh"]