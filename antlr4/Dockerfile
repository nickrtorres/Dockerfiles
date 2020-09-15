FROM ubuntu:latest

RUN apt update -y && apt upgrade -y && apt update -y
RUN apt install -y default-jdk unzip wget

RUN mkdir /opt/gradle
RUN cd /tmp && wget https://services.gradle.org/distributions/gradle-6.6.1-bin.zip && \
    unzip -d /opt/gradle /tmp/gradle-6.6.1-bin.zip

#
# This is a direct copy of the gradle Dockerfile up until this point.
# Eventually this should use a [multistage build]
# 
# [multistage build]: https://docs.docker.com/develop/develop-images/multistage-build/
#

RUN cd /usr/local/lib/ && wget https://www.antlr.org/download/antlr-4.8-complete.jar

COPY etc/antlr4 /usr/local/bin
COPY etc/grun /usr/local/bin

ENV CLASSPATH = ".:/usr/local/lib/antlr-4.8-complete.jar:$CLASSPATH"
ENV PATH = "$PATH:/opt/gradle/gradle-6.6.1/bin"
