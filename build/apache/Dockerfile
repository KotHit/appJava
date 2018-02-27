FROM centos:latest
MAINTAINER pasha <pasha.kudrinskiy@gmail.com>

RUN yum update -y && yum upgrade -y && yum install -y httpd

RUN awk -v n=1 -v s='LoadModule proxy_module modules/mod_proxy.so \n<VirtualHost *:80>\nProxyPreserveHost On\nProxyPass / http://172.18.0.2:8080/\nProxyPassReverse / http://172.18.0.2:8080/\n</VirtualHost>' 'NR == n {print s} {print}' /etc/httpd/conf/httpd.conf > /etc/httpd/conf/temp_httpd.tmp && mv /etc/httpd/conf/temp_httpd.tmp /etc/httpd/conf/httpd.conf

EXPOSE 80

CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

