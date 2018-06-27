FROM base/archlinux
MAINTAINER byidi <contact@byidi.fr>

RUN pacman --sync --noconfirm --refresh --sysupgrade
RUN pacman --sync --noconfirm nginx
RUN pacman -Scc --noconfirm

RUN mkdir -p /etc/nginx/sites-enabled

ADD ./conf/nginx.conf /etc/nginx/nginx.conf
ADD ./conf/sites/ /etc/nginx/sites-enabled/

ONBUILD RUN rm /etc/nginx/sites-enabled/00-default.conf

EXPOSE 80
EXPOSE 443

ENTRYPOINT ["nginx", "-g", "daemon off;"]
