# syntax=docker/dockerfile:1
FROM ubuntu:20.04
RUN apt update >/dev/null 2>/dev/null
ARG DEBIAN_FRONTEND=noninteractive
RUN  $(echo "12";) | apt-get install -y apache2 >/dev/null 2>/dev/null
RUN apt-get install -y libapache2-mod-security2 >/dev/null 2>/dev/null
RUN a2enmod proxy proxy_http ssl >/dev/null 2>/dev/null
COPY 000-default.conf /etc/apache2/sites-available/000-default.conf
EXPOSE 8080
CMD ["apache2ctl", "-D", "FOREGROUND"]

