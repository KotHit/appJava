FROM tomcat
MAINTAINER pasha <pasha.kudrinskiy@gmail.com>

RUN apt-get -y update && apt-get install wget -y
RUN cd /usr/local/tomcat/webapps
RUN wget https://tomcat.apache.org/tomcat-6.0-doc/appdev/sample/sample.war


EXPOSE 8080

