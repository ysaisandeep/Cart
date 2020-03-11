#This dockerfile for cart frontend
#DOCKERCOMMAND Options
FROM index.docker.io/centos:7
MAINTAINER mohanraz@gmail.com
RUN yum -y update
ADD config /opt
RUN chmod +x /opt/*
RUN source /opt/myappenv
RUN /opt/installpackage.sh
ADD code /var/www/html
ENV MY_DB_HOST_WRITE=test MY_DB_HOST_READ=test MY_DB_NAME=test MY_DB_USER=test MY_DB_PASS=test
EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]