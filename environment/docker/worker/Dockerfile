FROM webdevops/php:8.1-alpine

LABEL maintainer="danilopinotti@hotmail.com"

RUN docker-service-enable cron

# COPY config/horizon.conf /opt/docker/etc/supervisor.d/horizon-worker.conf

RUN echo "* * * * * /usr/local/bin/php /app/artisan schedule:run >> /dev/null 2>&1" >> /etc/crontabs/root

WORKDIR /app
