FROM php:8.2.4-apache

ENV TZ Asia/Tokyo
ENV APACHE_DOCUMENT_ROOT /var/www/mini-blog.localhost/web

COPY ./php.ini /usr/local/etc/php/conf.d/php.ini
COPY ./mini-blog.localhost.conf /etc/apache2/sites-available/mini-blog.localhost.conf

RUN a2ensite mini-blog.localhost.conf

RUN ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime \
  && echo ${TZ} > /etc/timezone

RUN apt-get update \
  && apt-get install -y \
    cron \
    vim \
  && docker-php-ext-install pdo_mysql

RUN sed -ri -e \
  's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' \
  /etc/apache2/sites-available/*.conf

RUN sed -ri -e \
  's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' \ 
  /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf
