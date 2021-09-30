FROM nginx

ARG ADMIN_EMAIL=info@domain.com

RUN apt-get update
RUN apt-get install certbot -y  --no-install-recommends
RUN apt-get install python3-certbot-nginx -y  --no-install-recommends
RUN apt-get install -y cron  --no-install-recommends
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN certbot register --agree-tos -m "${ADMIN_EMAIL}" -n

RUN echo "PATH=$PATH" > /etc/cron.d/certbot-renew \
      && echo "@monthly certbot renew --nginx >> /var/log/cron.log 2>&1" >>/etc/cron.d/certbot-renew \
      && crontab /etc/cron.d/certbot-renew
