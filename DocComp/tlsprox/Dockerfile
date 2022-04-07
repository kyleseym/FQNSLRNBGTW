# syntax=docker/dockerfile:1
FROM ubuntu:20.04
RUN apt update >/dev/null
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get install -y apache2 >/dev/null
RUN apt install openssl
RUN mkdir /usr/local/conf
RUN openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes -out /usr/local/conf/server.crt -keyout /usr/local/conf/server.key -subj "/C=US/ST=IL/L=Chicago/O=RIT/OU=CSEC731/CN=www.proxynet.com"
RUN a2enmod proxy proxy_http ssl >/dev/null
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf
EXPOSE 9020
CMD ["apache2ctl", "-D", "FOREGROUND"]

