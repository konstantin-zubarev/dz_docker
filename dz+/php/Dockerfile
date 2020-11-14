FROM alpine:3.12
RUN apk update && apk add php7-fpm \
	php7-mcrypt \
	php7-soap \
	php7-openssl \
	php7-gmp \
	php7-pdo_odbc \
	php7-json \
	php7-dom \
	php7-pdo \
	php7-zip \
	php7-mysqli \
	php7-sqlite3 \
	php7-apcu \
	php7-pdo_pgsql \
	php7-bcmath \
	php7-gd \
	php7-odbc \
	php7-pdo_mysql \
	php7-pdo_sqlite \
	php7-gettext \
	php7-xmlreader \
	php7-xmlrpc \
	php7-bz2 \
	php7-iconv \
	php7-pdo_dblib \
	php7-curl \
	php7-ctype
RUN adduser -D -g 'www' www \
&& mkdir /www \
&& chown -R www:www /www
EXPOSE 9000
ENTRYPOINT ["php-fpm7", "--nodaemonize"]
