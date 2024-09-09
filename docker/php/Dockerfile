FROM almalinux:9

RUN dnf -y install epel-release &&\
    dnf -y install https://rpms.remirepo.net/enterprise/remi-release-9.rpm &&\
    dnf -y upgrade &&\
    dnf -y install vim unzip &&\
    dnf -y module install nginx:1.24/common &&\
    dnf -y module reset php && sudo dnf -y module enable php:remi-7.4 &&\
    #CakePHP実行に最低限必要なパッケージをインストール
    dnf -y install php php-fpm php-imagick php-cli php-json php-devel php-gd php-pdo php-mysqlnd php-intl php-mbstring php-xml &&\
    dnf install phpMyAdmin