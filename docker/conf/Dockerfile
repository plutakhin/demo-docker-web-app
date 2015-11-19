FROM phusion/baseimage

MAINTAINER Dmitry Averbakh <adm@ruhub.com>

RUN apt-get update && apt-get install -y supervisor nginx

RUN apt-get update && apt-get install -y supervisor php5-common php5-cli php5-fpm php5-mcrypt php5-mysql php5-apcu php5-gd php5-imagick php5-curl php5-intl


RUN mkdir -p /var/log/supervisor

ADD supervisord.conf /etc/supervisor/conf.d/
ADD nginx.conf /etc/nginx/
ADD upstream.conf /etc/nginx/conf.d/
ADD client.conf /etc/nginx/sites-available/

RUN rm /etc/nginx/sites-enabled/default
RUN ln -s /etc/nginx/sites-available/client.conf /etc/nginx/sites-enabled/client

RUN usermod -u 1000 www-data

ADD supervisord.conf /etc/supervisor/conf.d/
ADD php.ini /etc/php5/fpm/conf.d/
ADD php.ini /etc/php5/cli/conf.d/
ADD pool.conf /etc/php5/fpm/pool.d/

RUN mkdir -p /var/log/supervisor
RUN usermod -u 1000 www-data

WORKDIR /var/www

EXPOSE 80

ENTRYPOINT ["/usr/bin/supervisord"]
