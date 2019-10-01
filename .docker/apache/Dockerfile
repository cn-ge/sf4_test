FROM debian:stretch

ENV HTTPD_PREFIX /usr/local/apache2
ENV PATH $HTTPD_PREFIX/bin:$PATH

RUN mkdir -p "$HTTPD_PREFIX" \
    && chown www-data:www-data "$HTTPD_PREFIX"

WORKDIR $HTTPD_PREFIX

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    apache2 \
    apache2-utils \
    curl \
    && rm -r /var/lib/apt/lists/*

# Configurer Apache afin qu’il transmette les requêtes à php lorsqu’elles nécessitent d’être interprétées
RUN a2enmod proxy_fcgi ssl rewrite proxy proxy_balancer proxy_http proxy_ajp
# Précise de manière globale à apache (pour tous les vhost) de transmettre toutes requête destinée à php
RUN a2enconf php7.2.3-fpm
RUN sed -i '/Global configuration/a \
ServerName localhost \
' /etc/apache2/apache2.conf

EXPOSE 80 443

RUN rm -f /run/apache2/apache2.pid

RUN usermod -u 1000 www-data
RUN usermod -G staff www-data

CMD apachectl  -DFOREGROUND -e info
