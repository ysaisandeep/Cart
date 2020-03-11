Use Centos 7  as my base image
FROM index.docker.io/centos:7
docker pull index.docker.io/centos:7

Update all the existing packages
RUN yum -y update
sh -c "yum -y update"

Install apache php php-gd php-myql
RUN yum -y install httpd php php-gd php-myql
sh -c "yum -y install httpd php php-gd php-myql"

copy the code to /var/www/html
ADD code /var/www/html
COPY code/* /var/www/html
ADD https://jfrog.f.c/xyz/xyz-1.VERSION.war /webapp
docker copy code/* xyz:/var/www/html 

Copy config file and source it
source <filename>

set DB enviroinment variable
MY_DB_HOST_WRITE=test
MY_DB_HOST_READ=test
MY_DB_NAME=test
MY_DB_USER=test
MY_DB_PASS=test

Start and Enable apache
CMD ["apachectl", "-D", "FOREGROUND"]
sh -c nohup apachectl -D FOREGROUND
