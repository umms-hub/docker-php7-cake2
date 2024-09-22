FROM almalinux:9

RUN dnf -y upgrade \
&& dnf -y module install nginx:1.24/common \
&& dnf -y install procps \
&& dnf clean all

# use volume
#COPY nginx.conf /etc/nginx/
#COPY default.conf /etc/nginx/default.d/

WORKDIR /var/www/html

CMD ["/usr/sbin/init"]