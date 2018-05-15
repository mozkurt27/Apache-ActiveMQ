FROM openjdk:8

MAINTAINER Muhammed ÖZKURT <mozkurt@partnera.com>


ENV ACTIVEMQ_VERSION 5.15.3
ENV TOMCAT_VERSION 9.0.1
ENV TOMCAT apache-tomcat-$TOMCAT_VERSION
ENV CATALINA_HOME /usr/local/$TOMCAT
ENV ACTIVEMQ apache-activemq-$ACTIVEMQ_VERSION
ENV ACTIVEMQ_HOME /usr/local/$ACTIVEMQ
ENV PATH $ACTIVEMQ_HOME/bin:$CATALINA_HOME/bin:$PATH

RUN \
    curl http://archive.apache.org/dist/activemq/$ACTIVEMQ_VERSION/$ACTIVEMQ-bin.tar.gz -o /usr/local/$ACTIVEMQ-bin.tar.gz && \
    tar -xzvf /usr/local/$ACTIVEMQ-bin.tar.gz -C /usr/local/ && \
    rm /usr/local/$ACTIVEMQ-bin.tar.gz 

RUN \
    curl https://archive.apache.org/dist/tomcat/tomcat-9/v$TOMCAT_VERSION/bin/$TOMCAT.tar.gz -o /usr/local/$TOMCAT.tar.gz && \
    tar -xzvf /usr/local/$TOMCAT.tar.gz -C /usr/local/ && \
    rm /usr/local/$TOMCAT.tar.gz

WORKDIR $ACTIVEMQ_HOME

EXPOSE 61616 8161 8080

CMD bin/activemq start && \
    /usr/local/$TOMCAT/bin/catalina.sh run
