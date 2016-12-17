FROM php:7-fpm

RUN apt-get update
RUN apt-get install supervisor git -y
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
COPY ./supervisor/supervisord.conf /etc/supervisor/conf.d/1-supervisord.conf
COPY ./supervisor/php.conf /etc/supervisor/conf.d/2-php.conf

WORKDIR /var/www

CMD ["/usr/bin/supervisord"]
