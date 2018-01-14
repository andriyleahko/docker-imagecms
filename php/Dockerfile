FROM cytopia/php-fpm-5.5

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

RUN cd /tmp \
    && curl -o ioncube.tar.gz http://downloads3.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz \
    && tar -xvvzf ioncube.tar.gz \
    && mv ioncube/ioncube_loader_lin_5.5.so /etc/php.d/ioncube_loader_lin_5.5.so \
    && rm -Rf ioncube.tar.gz ioncube \
    && echo "zend_extension=/etc/php.d/ioncube_loader_lin_5.5.so" > /etc/php.d/00_docker-php-ext-ioncube_loader_lin_5.5.ini


