FROM java:8

ENV http_proxy '%PROXY%'
ENV https_proxy '%PROXY%'

ADD https://bintray.com/artifact/download/jfrog/artifactory/jfrog-artifactory-oss-4.1.0.zip?direct artifactory.zip
RUN unzip artifactory.zip

RUN sed -i -e 's/Xmx2g/Xmx512m/g' artifactory-*/bin/artifactory.default

EXPOSE 8081

ENTRYPOINT artifactory-*/bin/artifactory.sh

ENV http_proxy=
ENV https_proxy=
