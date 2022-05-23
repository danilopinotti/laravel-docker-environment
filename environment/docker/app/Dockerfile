FROM webdevops/php:7.4-alpine

LABEL maintainer="danilopinotti@hotmail.com"

RUN pecl config-set php_ini /opt/docker/etc/php/php.ini \
  && pear config-set php_ini /opt/docker/etc/php/php.ini \
  && apk upgrade --update \
  && apk add curl nano

WORKDIR /app
