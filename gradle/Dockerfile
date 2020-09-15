FROM ubuntu:latest

RUN apt update -y && apt upgrade -y && apt update -y
RUN apt install -y default-jdk unzip wget

RUN mkdir /opt/gradle
RUN cd /tmp && wget https://services.gradle.org/distributions/gradle-6.6.1-bin.zip && \
    unzip -d /opt/gradle /tmp/gradle-6.6.1-bin.zip

ENV PATH = "$PATH:/opt/gradle/gradle-6.6.1/bin"
