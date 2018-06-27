FROM base/archlinux
MAINTAINER byidi <contact@byidi.fr>

RUN pacman --sync --noconfirm --refresh --sysupgrade
RUN pacman --sync --noconfirm php-fpm php-gd php-ldap php-sqlite php-pgsql
RUN pacman -Scc --noconfirm

RUN sed -i '/^listen/c listen = 0.0.0.0:9000' /etc/php/php-fpm.d/www.conf
RUN sed -i -E 's/^;(security.limit_extensions = )(.*)/\1/' /etc/php/php-fpm.d/www.conf

EXPOSE 9000

CMD ["/usr/bin/php-fpm", "-F"]
