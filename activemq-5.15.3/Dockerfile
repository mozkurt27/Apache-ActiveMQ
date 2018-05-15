FROM openjdk:8

MAINTAINER Muhammed ÖZKURT <mozkurt@partnera.com>


ENV ACTIVEMQ_VERSION 5.15.3
ENV ACTIVEMQ apache-activemq-$ACTIVEMQ_VERSION
ENV ACTIVEMQ_HOME /usr/local/$ACTIVEMQ
ENV PATH $ACTIVEMQ_HOME/bin:$PATH

RUN \
    curl http://archive.apache.org/dist/activemq/$ACTIVEMQ_VERSION/$ACTIVEMQ-bin.tar.gz -o /usr/local/$ACTIVEMQ-bin.tar.gz && \
    tar -xzvf /usr/local/$ACTIVEMQ-bin.tar.gz -C /usr/local/ && \
    rm /usr/local/$ACTIVEMQ-bin.tar.gz 


WORKDIR $ACTIVEMQ_HOME

EXPOSE 61616 8161

CMD bin/activemq console
