FROM busybox
MAINTAINER Nazar Mokrynskyi <nazar@mokrynskyi.com>

# Create main directories for MySQL (MariaDB), Nginx and SSH

RUN mkdir /etc/mysql && \
	mkdir /var/lib/mysql && \
	mkdir /var/log/mysql && \

	mkdir -p /usr/share/nginx/html && \
	mkdir /var/log/nginx && \

	mkdir -p /usr/local/etc && \

# Setting directories owners for MySQL (MariaDB) and Nginx (like they are in corresponding official images)

	chown 999:999 /var/lib/mysql && \
	chown 999:999 /var/log/mysql && \

	chown 1000:1000 /usr/share/nginx/html && \
	chown 1000:1000 /var/log/nginx && \

# Create /data directory and inside symlinks for all other directories

	mkdir /data && \

	mkdir /data/.ssh && \

	mkdir /data/mysql && \
	ln -s /etc/mysql /data/mysql/config && \
	ln -s /var/log/mysql /data/mysql/log && \
	ln -s /var/lib/mysql /data/mysql/data && \

	mkdir /data/nginx && \
	ln -s /etc/nginx /data/nginx/config && \
	ln -s /var/log/nginx /data/nginx/log && \
	ln -s /user/share/nginx/html /data/nginx/www && \

	mkdir /data/php && \
	ln -s /usr/local/etc /data/php/config

VOLUME	/data \
		/etc/mysql \
		/etc/nginx \
		/usr/local/etc \
		/var/lib/mysql \
		/var/log/mysql \
		/var/log/nginx