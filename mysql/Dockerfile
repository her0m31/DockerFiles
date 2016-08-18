FROM centos:7

RUN groupadd -r mysql && useradd -r -g mysql mysql

RUN yum update && yum install -y http://dev.mysql.com/get/mysql57-community-release-el7-7.noarch.rpm \
  mysql-community-server

EXPOSE 3306
CMD ["mysqld"]
