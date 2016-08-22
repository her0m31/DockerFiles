# App ==Apache and php70==
FROM centos:7

RUN adduser her8m

RUN yum install -y \
  httpd \
  git \
  unzip \
  epel-release

RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm

RUN yum install -y --enablerepo=remi,remi-php70 \
  php \
  php-devel \
  php-mbstring \
  php-pdo php-gd \
  php-mysql \
  php-mcrypt \
  php-tokenizer

RUN rm -rf /var/www/*

RUN echo "HTTP server running on guest" > /var/www/index.html
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
RUN composer global require 'laravel/installer'
RUN echo 'export PATH=~/.composer/vendor/laravel/installer:$PATH' >> ~/.bashrc

ADD ./httpd.conf /etc/httpd/conf/

EXPOSE 80
CMD /usr/sbin/httpd -D FOREGROUND 
