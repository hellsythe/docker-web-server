FROM ubuntu

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get -y install \
             software-properties-common

# Install Apache and PHP
RUN apt-get -y install apache2 \
    --no-install-recommends && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN a2enmod rewrite headers expires proxy_fcgi mpm_event ssl http2

RUN a2dismod mpm_prefork

#RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/ssl-cert-snakeoil.key -out /etc/ssl/certs/ssl-cert-snakeoil.pem

CMD ["/usr/sbin/apache2ctl", "-DFOREGROUND"]
