FROM achtachtel/debian-dotdeb:wheezy

MAINTAINER Marcel Brand <marcel.brand@achtachtel.de>

# Add dotdeb repository for php 5.5 to sources.list.d
ADD ./dotdeb-php.list /etc/apt/sources.list.d/

# Update and install apache2 and php5
RUN apt-get update && apt-get install -y \
    apache2 \
    php5 \
    php5-curl \
    php5-mysql \
    && apt-get clean

RUN /usr/sbin/a2enmod ssl && \
    /usr/sbin/a2enmod rewrite && \
    /usr/sbin/a2enmod php5

EXPOSE 80
EXPOSE 443

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]