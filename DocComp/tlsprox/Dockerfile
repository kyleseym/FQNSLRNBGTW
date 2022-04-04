# syntax=docker/dockerfile:1
FROM ubuntu:20.04
RUN apt update >/dev/null
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get install -y apache2 >/dev/null
RUN a2enmod proxy proxy_http ssl >/dev/null
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf
COPY priv.pem /home/certs/priv.pem
COPY pubcert.pem /home/certs/pubcert.pem
EXPOSE 443
CMD ["apache2ctl", "-D", "FOREGROUND"]

