FROM almalinux:9

RUN dnf -y install epel-release \
&& dnf -y install https://rpms.remirepo.net/enterprise/remi-release-9.rpm \
&& dnf -y upgrade \
&& dnf -y install vim unzip \
#RUN dnf -y module install nginx:1.24/common
&& dnf module reset php \
&& dnf -y module install php:remi-7.4 \
&& dnf -y install php php-fpm php-imagick php-cli php-json php-devel php-gd php-pdo php-mysqlnd php-intl php-mbstring php-xml
#&& dnf -y install phpMyAdmin

# install composer
WORKDIR /tmp
RUN dnf -y install unzip wget \
&& wget https://getcomposer.org/installer -O composer-installer.php \
&& php composer-installer.php --filename=composer --install-dir=/usr/local/bin \
&& composer self-update \
&& dnf clean all

# unix socket
RUN mkdir -p /run/php-fpm

# setting files
COPY php.ini /etc/
COPY www.conf /etc/php-fpm.d/

RUN chown nginx:nginx /var/lib/php/session
RUN chown nginx:nginx -R /var/www/html

WORKDIR /var/www/html