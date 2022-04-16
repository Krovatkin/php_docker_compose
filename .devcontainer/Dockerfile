FROM wordpress:5.9.0

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN printf "zend_extension=xdebug\n\
[xdebug]\n\
xdebug.mode=develop,debug\n\
xdebug.client_host=localhost\n\
xdebug.start_with_request=yes" > /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini