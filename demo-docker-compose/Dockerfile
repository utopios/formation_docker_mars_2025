# Application build et run
#### stage build
FROM php:8.1-cli AS builder

RUN apt update && apt install git -y

RUN useradd -ms /bin/bash admin

RUN git clone https://github.com/NouvelleTechno/e-commerce-Symfony-6 /app

WORKDIR /app

RUN chown -R admin:admin /app

RUN chmod 755 /app

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

USER admin

RUN composer install 

#### stage run
FROM php:8.1-apache
RUN useradd -ms /bin/bash admin
COPY --from=builder --chown=admin:admin /app/ /var/www/html/

ENV APACHE_DOCUMENT_ROOT=/var/www/html/public

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/conf-available/*.conf /etc/apache2/apache2.conf

RUN a2enmod rewrite

EXPOSE 80

CMD [ "apache2-foreground" ]