FROM centos:7

# RUN groupadd -r mysql && useradd -r -g mysql mysql

RUN yum install -y \
  http://dev.mysql.com/get/mysql57-community-release-el7-7.noarch.rpm

RUN yum update -y

RUN yum install -y \
  mysql-community-server

EXPOSE 3306
CMD ["mysqld"]
