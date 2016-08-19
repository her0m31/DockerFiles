# App ==Apache and php70==
FROM centos:7

RUN groupadd -r her8m && useradd -r -g her8m her8m

RUN yum install -y \
  httpd \
  git \
  epel-release

RUN yum install -y \
  --enablerepo=remi,remi-php70 \
  php \
  php-devel \
  php-mbstring \
  php-pdo \
  php-gd \
  php-mysql \
  php-mcrypt \
  php-tokenizer

RUN echo "HTTP server running on guest" > /var/www/html/index.html
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
RUN composer global require 'laravel/installer'
RUN echo 'export PATH=~/.composer/vendor/laravel/installer:$PATH' >> ~/.bashrc


EXPOSE 80
CMD httpd -D FOREGROUND 
