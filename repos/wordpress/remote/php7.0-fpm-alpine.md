## `wordpress:php7.0-fpm-alpine`

```console
$ docker pull wordpress@sha256:6cc40315bc5109970e2472fe911223184874ba3bb10d30f492e83f471f23a667
```

-	Platforms:
	-	linux; amd64

### `wordpress:php7.0-fpm-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **40.7 MB (40743453 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:de74c287e059fa73e088398ff4e926b65ec4809d698dbac681d2007192db9698`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:13 GMT
ADD file:eeed5f514a35d18fcd9cbfe6c40c582211020bffdd53e4799018d33826fe5067 in / 
# Tue, 27 Dec 2016 19:18:54 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Tue, 27 Dec 2016 19:18:56 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Tue, 27 Dec 2016 19:18:57 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Tue, 27 Dec 2016 19:19:15 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 27 Dec 2016 19:19:16 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 27 Dec 2016 19:31:20 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Tue, 27 Dec 2016 19:31:20 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 27 Dec 2016 19:31:21 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 27 Dec 2016 19:31:22 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 24 Jan 2017 19:07:31 GMT
ENV GPG_KEYS=1A4E8B7277C42E53DBA9C7B9BCAA30EA9C0D5763 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Fri, 17 Feb 2017 19:19:37 GMT
ENV PHP_VERSION=7.0.16
# Fri, 17 Feb 2017 19:19:38 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.0.16.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.0.16.tar.xz.asc/from/this/mirror
# Fri, 17 Feb 2017 19:19:38 GMT
ENV PHP_SHA256=244ac39bc657448962860aa7a590e4417f68513ad5e86ee2727b1328b0537309 PHP_MD5=6161aba9d24322d889da5d2ff944bddf
# Fri, 17 Feb 2017 19:19:58 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Fri, 17 Feb 2017 19:20:09 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Fri, 17 Feb 2017 19:24:49 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(getconf _NPROCESSORS_ONLN)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps
# Fri, 17 Feb 2017 19:25:05 GMT
COPY multi:5c1cc33896847ec6f8a128a1494e83c37aea885824061e1b8e308f9e09499956 in /usr/local/bin/ 
# Fri, 17 Feb 2017 19:25:05 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Fri, 17 Feb 2017 19:25:06 GMT
WORKDIR /var/www/html
# Fri, 17 Feb 2017 19:25:07 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Fri, 17 Feb 2017 19:25:21 GMT
EXPOSE 9000/tcp
# Fri, 17 Feb 2017 19:25:22 GMT
CMD ["php-fpm"]
# Fri, 17 Feb 2017 21:13:58 GMT
RUN apk add --no-cache 		bash 		sed
# Fri, 17 Feb 2017 21:14:30 GMT
RUN set -ex; 		apk add --no-cache --virtual .build-deps 		libjpeg-turbo-dev 		libpng-dev 	; 		docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr; 	docker-php-ext-install gd mysqli opcache; 		runDeps="$( 		scanelf --needed --nobanner --recursive 			/usr/local/lib/php/extensions 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)"; 	apk add --virtual .wordpress-phpexts-rundeps $runDeps; 	apk del .build-deps
# Fri, 17 Feb 2017 21:14:31 GMT
RUN { 		echo 'opcache.memory_consumption=128'; 		echo 'opcache.interned_strings_buffer=8'; 		echo 'opcache.max_accelerated_files=4000'; 		echo 'opcache.revalidate_freq=2'; 		echo 'opcache.fast_shutdown=1'; 		echo 'opcache.enable_cli=1'; 	} > /usr/local/etc/php/conf.d/opcache-recommended.ini
# Fri, 17 Feb 2017 21:14:31 GMT
VOLUME [/var/www/html]
# Fri, 17 Feb 2017 21:14:32 GMT
ENV WORDPRESS_VERSION=4.7.2
# Fri, 17 Feb 2017 21:14:32 GMT
ENV WORDPRESS_SHA1=7b687f1af589c337124e6247229af209ec1d52c3
# Fri, 17 Feb 2017 21:14:35 GMT
RUN set -ex; 	curl -o wordpress.tar.gz -fSL "https://wordpress.org/wordpress-${WORDPRESS_VERSION}.tar.gz"; 	echo "$WORDPRESS_SHA1 *wordpress.tar.gz" | sha1sum -c -; 	tar -xzf wordpress.tar.gz -C /usr/src/; 	rm wordpress.tar.gz; 	chown -R www-data:www-data /usr/src/wordpress
# Fri, 17 Feb 2017 21:14:36 GMT
COPY file:b5c332f80307d4248d07b035890c0ea453c1157d9e1732225f83f63d851392b5 in /usr/local/bin/ 
# Fri, 17 Feb 2017 21:14:36 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 17 Feb 2017 21:14:37 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:b7f33cc0b48ea4fb2f0745def58c25483a5f6b7aed5b41ce8f1cb6e17f5723cf`  
		Last Modified: Tue, 27 Dec 2016 18:18:49 GMT  
		Size: 2.3 MB (2313090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7d6bcc00046712ac206a652bc839e40f8f4e6f580123a1a7ac21b92fd757364`  
		Last Modified: Tue, 27 Dec 2016 21:08:34 GMT  
		Size: 1.0 MB (1048526 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f3822a33fdb297624accfaaaa052a8f4850ae1450aa3edeefcfe0e693a54e689`  
		Last Modified: Tue, 27 Dec 2016 21:08:33 GMT  
		Size: 1.3 KB (1273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49a47789bbdf4b2c131bf8ba82cc36e09ad0b022627f22862898cae483511aeb`  
		Last Modified: Tue, 27 Dec 2016 21:08:33 GMT  
		Size: 166.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23a98aeaa6db5ed9aea53098ff291dc259ee8d7628673f87f0bc734ad44a878a`  
		Last Modified: Fri, 17 Feb 2017 19:47:29 GMT  
		Size: 12.8 MB (12760664 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75bbee5d62e36e5adbc9fbae96eaf16ec3f1a6f19678357fa4385d5ccbcd020d`  
		Last Modified: Fri, 17 Feb 2017 19:47:24 GMT  
		Size: 482.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:575b74a866818f04cbb0a79b9a517f8defbbaa23acc8a09b86de8597b2115756`  
		Last Modified: Fri, 17 Feb 2017 19:47:29 GMT  
		Size: 15.5 MB (15467089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78db0856b95fc2d0eae9c25a951a1dc23e406477a436b1c5407911993c805f10`  
		Last Modified: Fri, 17 Feb 2017 19:47:24 GMT  
		Size: 2.0 KB (1999 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da1dc1adb0f4ffdabe6e02d269055c9f63c6a01728327e5700a513e421945017`  
		Last Modified: Fri, 17 Feb 2017 19:47:23 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1195409d6e4c6ed0829bde37ec3969dc96c4f7968492e341aaa6bba43d79881`  
		Last Modified: Fri, 17 Feb 2017 19:47:24 GMT  
		Size: 7.7 KB (7673 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:972b52c9088c9e66676a1f5d29fdf7e77a84b375deb1e16a74617f936bf07396`  
		Last Modified: Fri, 17 Feb 2017 21:27:14 GMT  
		Size: 590.0 KB (590049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:20af10f2652d4817dd234921f9bfc1117eb540d12394ab1b7f7fc4ce990d41f2`  
		Last Modified: Fri, 17 Feb 2017 21:27:13 GMT  
		Size: 721.4 KB (721426 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:efd2141ed7358a9a7a074b80e245d04da1be9ac3b31976f7aed8c1fbe6bd511a`  
		Last Modified: Fri, 17 Feb 2017 21:27:14 GMT  
		Size: 321.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c93faeecfa58e6da940ae93331d021f73b2e0a33071bb9c8c5c46f4cd8340d0c`  
		Last Modified: Fri, 17 Feb 2017 21:27:17 GMT  
		Size: 7.8 MB (7827441 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15e2bff86fb56ee605eb149b1700c96867e6631f4ff1fc877791bce897c88b4e`  
		Last Modified: Fri, 17 Feb 2017 21:27:14 GMT  
		Size: 3.1 KB (3125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
