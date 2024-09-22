FROM almalinux:9

RUN dnf -y upgrade \
&& dnf -y module install nginx:1.24/common \
&& dnf -y install procps \
&& dnf clean all

#COPY nginx.conf /etc/nginx/
#COPY default.conf /etc/nginx/default.d/

#WORKDIR /home/${USER_NAME}
WORKDIR /var/www/html

CMD ["systemctl enable --now nginx"]