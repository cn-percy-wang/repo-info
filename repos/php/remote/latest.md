## `php:latest`

```console
$ docker pull php@sha256:15e71db34e37e1eb39ea32dfde094b23919bda6a703d9204ba3543474885e230
```

-	Platforms:
	-	linux; amd64

### `php:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **153.0 MB (152955060 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9364fb774af9e2cf7758065a2659950ffe735e7fd57f1d2a39ff129db36eaf8e`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["php","-a"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 18:54:13 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 17 Jan 2017 18:54:39 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 17 Jan 2017 18:54:39 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 17 Jan 2017 18:54:40 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 17 Jan 2017 18:54:40 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jan 2017 18:54:40 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jan 2017 18:54:41 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 24 Jan 2017 18:05:33 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Mon, 20 Feb 2017 18:42:34 GMT
ENV PHP_VERSION=7.1.2
# Mon, 20 Feb 2017 18:42:35 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.2.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.2.tar.xz.asc/from/this/mirror
# Mon, 20 Feb 2017 18:42:35 GMT
ENV PHP_SHA256=d815a0c39fd57bab1434a77ff0610fb507c22f790c66cd6f26e27030c4b3e971 PHP_MD5=d79afea1870277c86fac903566fb6c5d
# Mon, 20 Feb 2017 18:42:46 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 20 Feb 2017 18:42:47 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Mon, 20 Feb 2017 18:46:23 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Mon, 20 Feb 2017 18:46:25 GMT
COPY multi:b2b2a1a4e3c0f0bb8ebdcd527fca158bfce5138468926263f86e5bb0cb41970f in /usr/local/bin/ 
# Mon, 20 Feb 2017 18:46:25 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Mon, 20 Feb 2017 18:46:26 GMT
CMD ["php" "-a"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:568dce68541a55fd0fb33021383e3921145275a1f87d925f37f1246b682baf0b`  
		Last Modified: Wed, 18 Jan 2017 03:05:48 GMT  
		Size: 77.6 MB (77606810 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a832068e64c0a907e1585adac98802eb69cf9fc878ba00941d59e7be57c4b93`  
		Last Modified: Wed, 18 Jan 2017 03:05:21 GMT  
		Size: 178.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b62a5cfb45ac2e2e609c0ea99ce317a370db2559693f2fe4cf400ed22dc4a6b3`  
		Last Modified: Mon, 20 Feb 2017 19:10:19 GMT  
		Size: 12.9 MB (12891389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84754dd6bcca7ee9d916f3cf7172482b3b5057726b17d1f4faa9b37cd676f880`  
		Last Modified: Mon, 20 Feb 2017 19:10:18 GMT  
		Size: 492.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af90e1b6dc7c81ff03763a49ba29c6d8e35fa3949220543190f2b4a01df32f9b`  
		Last Modified: Mon, 20 Feb 2017 19:10:20 GMT  
		Size: 11.1 MB (11092972 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0efc7f77d669907761f03fa6ceab1b418d5e09fdf702607e94d70342bb2bbc9e`  
		Last Modified: Mon, 20 Feb 2017 19:10:17 GMT  
		Size: 2.0 KB (2009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
