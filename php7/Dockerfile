FROM rasteiner/common-php-apache:php7

RUN apt-get update &&\
    apt-get install --no-install-recommends --assume-yes --quiet ca-certificates curl git &&\
    rm -rf /var/lib/apt/lists/*

RUN pecl install xdebug-2.6.1 && docker-php-ext-enable xdebug
RUN echo 'zend_extension="/usr/local/lib/php/extensions/no-debug-non-zts-20151012/xdebug.so"' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_port=9000' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_enable=1' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_host=192.168.1.109' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_mode=req' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.profiler_enable = 1' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.profiler_output_name = xdebug.out.%t' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.profiler_output_dir = /var/www/html/.profiler' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.profiler_enable_trigger = 1' >> /usr/local/etc/php/php.ini

RUN usermod -u 1000 www-data
