FROM almalinux:9

RUN dnf -y install epel-release
RUN dnf -y install https://rpms.remirepo.net/enterprise/remi-release-9.rpm
RUN dnf -y upgrade
RUN dnf -y install vim unzip
#RUN dnf -y module install nginx:1.24/common
RUN dnf module reset php 
RUN dnf -y module install php:remi-7.4
#CakePHP実行に最低限必要なパッケージをインストール
RUN dnf -y install php php-fpm php-imagick php-cli php-json php-devel php-gd php-pdo php-mysqlnd php-intl php-mbstring php-xml
RUN dnf -y install phpMyAdmin

# install composer
RUN dnf -y install unzip wget
WORKDIR /tmp
RUN wget https://getcomposer.org/installer -O composer-installer.php
RUN php composer-installer.php --filename=composer --install-dir=/usr/local/bin
RUN composer self-update

# unix socket
RUN mkdir /var/run/php-fpm
VOLUME ["/var/run/php-fpm"]