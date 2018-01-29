# Based from: https://medium.com/dev-tricks/apache-and-php-on-docker-44faef716150#.rrpzcyopr
FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get -y install \
    curl \
    apache2 libapache2-mod-php \
    php php-mysql php-mcrypt php-xdebug

RUN a2enmod php7.1
RUN a2enmod rewrite

# Update the default apache site with the config we created.
ADD conf/apache-config.conf /etc/apache2/sites-enabled/000-default.conf

# By default start up apache in the foreground, override with /bin/bash for interative.
CMD /usr/sbin/apache2ctl -D FOREGROUND