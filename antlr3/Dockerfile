FROM ubuntu:latest

RUN apt update -y && apt upgrade -y && apt update -y
RUN apt install -y curl default-jdk

RUN cd /usr/local/lib && curl -LO http://www.antlr3.org/download/antlr-3.5.2-complete-no-st3.jar
ENV CLASSPATH=".:/usr/local/lib/antlr-3.5.2-complete-no-st3.jar:$CLASSPATH"

RUN echo "alias antlr3='java -jar /usr/local/lib/antlr-3.5.2-complete-no-st3.jar'" >> ~/.bashrc
