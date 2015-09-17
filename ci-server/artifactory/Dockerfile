FROM ubuntu:latest

ENV http_proxy '<PROXY>'
ENV https_proxy '<PROXY>'

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" >> /etc/apt/sources.list
RUN apt-get update

RUN apt-get install -y openjdk-7-jre-headless unzip

ADD http://dl.bintray.com/jfrog/artifactory/artifactory-3.9.4.zip?direct artifactory.zip
RUN unzip artifactory.zip

RUN sed -i -e 's/Xmx2g/Xmx512m/g' artifactory-*/bin/artifactory.default

EXPOSE 8081

ENTRYPOINT artifactory-*/bin/artifactory.sh

ENV http_proxy=
ENV https_proxy=
