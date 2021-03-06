<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `postgres`

-	[`postgres:9.6.2`](#postgres962)
-	[`postgres:9.6`](#postgres96)
-	[`postgres:9`](#postgres9)
-	[`postgres:latest`](#postgreslatest)
-	[`postgres:9.6.2-alpine`](#postgres962-alpine)
-	[`postgres:9.6-alpine`](#postgres96-alpine)
-	[`postgres:9-alpine`](#postgres9-alpine)
-	[`postgres:alpine`](#postgresalpine)
-	[`postgres:9.5.6`](#postgres956)
-	[`postgres:9.5`](#postgres95)
-	[`postgres:9.5.6-alpine`](#postgres956-alpine)
-	[`postgres:9.5-alpine`](#postgres95-alpine)
-	[`postgres:9.4.11`](#postgres9411)
-	[`postgres:9.4`](#postgres94)
-	[`postgres:9.4.11-alpine`](#postgres9411-alpine)
-	[`postgres:9.4-alpine`](#postgres94-alpine)
-	[`postgres:9.3.16`](#postgres9316)
-	[`postgres:9.3`](#postgres93)
-	[`postgres:9.3.16-alpine`](#postgres9316-alpine)
-	[`postgres:9.3-alpine`](#postgres93-alpine)
-	[`postgres:9.2.20`](#postgres9220)
-	[`postgres:9.2`](#postgres92)
-	[`postgres:9.2.20-alpine`](#postgres9220-alpine)
-	[`postgres:9.2-alpine`](#postgres92-alpine)

## `postgres:9.6.2`

```console
$ docker pull postgres@sha256:ff99a5301e7c81cba881e3fbdbf4df5a068683765249ba5ea5694a83747509d4
```

-	Platforms:
	-	linux; amd64

### `postgres:9.6.2` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.8 MB (101796496 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ecd991538a0fbb77f8a0327d5ef92b4fe1c50da57719c4a8e810b399199e53e3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:36:30 GMT
ENV PG_MAJOR=9.6
# Fri, 10 Feb 2017 00:28:09 GMT
ENV PG_VERSION=9.6.2-1.pgdg80+1
# Fri, 10 Feb 2017 00:28:10 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:28:58 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:29:00 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:29:01 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:29:02 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:29:03 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:29:04 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:29:05 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:29:06 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:29:08 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:29:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:29:09 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:29:10 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebd975526cfbc326e37b386f779043722326bc30eb7af09d6287d13b6c7a4941`  
		Last Modified: Fri, 10 Feb 2017 00:53:19 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63112c9f9e8d99401b0808250fbf24503a13db0507196c14716828246f774e8c`  
		Last Modified: Fri, 10 Feb 2017 00:53:39 GMT  
		Size: 42.3 MB (42337768 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:512813961d560004edbb53bdbc4aed70036d0e2f9c74c85819db5348624387df`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 7.1 KB (7126 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71e6df12323a9a6f2d2f516263dae9e3211c5d176953fa0536fd73c844af0be0`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a180292adaf327d4ef98e37aa7a8653dbee2181f58235ad24a362d2399bb22d0`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa13b6035e19d5e0e199c8f0822a8421c46ecd87f1f66ee168cb7d6c2eec2a5f`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 1.7 KB (1692 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad671404dcdb5ca1fd8e3b2f016703fd7c5aaea2d5f303b8558fd0a726307ae7`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.6`

```console
$ docker pull postgres@sha256:ff99a5301e7c81cba881e3fbdbf4df5a068683765249ba5ea5694a83747509d4
```

-	Platforms:
	-	linux; amd64

### `postgres:9.6` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.8 MB (101796496 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ecd991538a0fbb77f8a0327d5ef92b4fe1c50da57719c4a8e810b399199e53e3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:36:30 GMT
ENV PG_MAJOR=9.6
# Fri, 10 Feb 2017 00:28:09 GMT
ENV PG_VERSION=9.6.2-1.pgdg80+1
# Fri, 10 Feb 2017 00:28:10 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:28:58 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:29:00 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:29:01 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:29:02 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:29:03 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:29:04 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:29:05 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:29:06 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:29:08 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:29:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:29:09 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:29:10 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebd975526cfbc326e37b386f779043722326bc30eb7af09d6287d13b6c7a4941`  
		Last Modified: Fri, 10 Feb 2017 00:53:19 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63112c9f9e8d99401b0808250fbf24503a13db0507196c14716828246f774e8c`  
		Last Modified: Fri, 10 Feb 2017 00:53:39 GMT  
		Size: 42.3 MB (42337768 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:512813961d560004edbb53bdbc4aed70036d0e2f9c74c85819db5348624387df`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 7.1 KB (7126 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71e6df12323a9a6f2d2f516263dae9e3211c5d176953fa0536fd73c844af0be0`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a180292adaf327d4ef98e37aa7a8653dbee2181f58235ad24a362d2399bb22d0`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa13b6035e19d5e0e199c8f0822a8421c46ecd87f1f66ee168cb7d6c2eec2a5f`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 1.7 KB (1692 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad671404dcdb5ca1fd8e3b2f016703fd7c5aaea2d5f303b8558fd0a726307ae7`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9`

```console
$ docker pull postgres@sha256:ff99a5301e7c81cba881e3fbdbf4df5a068683765249ba5ea5694a83747509d4
```

-	Platforms:
	-	linux; amd64

### `postgres:9` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.8 MB (101796496 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ecd991538a0fbb77f8a0327d5ef92b4fe1c50da57719c4a8e810b399199e53e3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:36:30 GMT
ENV PG_MAJOR=9.6
# Fri, 10 Feb 2017 00:28:09 GMT
ENV PG_VERSION=9.6.2-1.pgdg80+1
# Fri, 10 Feb 2017 00:28:10 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:28:58 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:29:00 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:29:01 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:29:02 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:29:03 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:29:04 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:29:05 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:29:06 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:29:08 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:29:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:29:09 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:29:10 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebd975526cfbc326e37b386f779043722326bc30eb7af09d6287d13b6c7a4941`  
		Last Modified: Fri, 10 Feb 2017 00:53:19 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63112c9f9e8d99401b0808250fbf24503a13db0507196c14716828246f774e8c`  
		Last Modified: Fri, 10 Feb 2017 00:53:39 GMT  
		Size: 42.3 MB (42337768 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:512813961d560004edbb53bdbc4aed70036d0e2f9c74c85819db5348624387df`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 7.1 KB (7126 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71e6df12323a9a6f2d2f516263dae9e3211c5d176953fa0536fd73c844af0be0`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a180292adaf327d4ef98e37aa7a8653dbee2181f58235ad24a362d2399bb22d0`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa13b6035e19d5e0e199c8f0822a8421c46ecd87f1f66ee168cb7d6c2eec2a5f`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 1.7 KB (1692 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad671404dcdb5ca1fd8e3b2f016703fd7c5aaea2d5f303b8558fd0a726307ae7`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:latest`

```console
$ docker pull postgres@sha256:ff99a5301e7c81cba881e3fbdbf4df5a068683765249ba5ea5694a83747509d4
```

-	Platforms:
	-	linux; amd64

### `postgres:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.8 MB (101796496 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ecd991538a0fbb77f8a0327d5ef92b4fe1c50da57719c4a8e810b399199e53e3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:36:30 GMT
ENV PG_MAJOR=9.6
# Fri, 10 Feb 2017 00:28:09 GMT
ENV PG_VERSION=9.6.2-1.pgdg80+1
# Fri, 10 Feb 2017 00:28:10 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:28:58 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:29:00 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:29:01 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:29:02 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:29:03 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:29:04 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:29:05 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:29:06 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:29:08 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:29:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:29:09 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:29:10 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebd975526cfbc326e37b386f779043722326bc30eb7af09d6287d13b6c7a4941`  
		Last Modified: Fri, 10 Feb 2017 00:53:19 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63112c9f9e8d99401b0808250fbf24503a13db0507196c14716828246f774e8c`  
		Last Modified: Fri, 10 Feb 2017 00:53:39 GMT  
		Size: 42.3 MB (42337768 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:512813961d560004edbb53bdbc4aed70036d0e2f9c74c85819db5348624387df`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 7.1 KB (7126 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71e6df12323a9a6f2d2f516263dae9e3211c5d176953fa0536fd73c844af0be0`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a180292adaf327d4ef98e37aa7a8653dbee2181f58235ad24a362d2399bb22d0`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa13b6035e19d5e0e199c8f0822a8421c46ecd87f1f66ee168cb7d6c2eec2a5f`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 1.7 KB (1692 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad671404dcdb5ca1fd8e3b2f016703fd7c5aaea2d5f303b8558fd0a726307ae7`  
		Last Modified: Fri, 10 Feb 2017 00:53:17 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.6.2-alpine`

```console
$ docker pull postgres@sha256:f501aae03fc31749599a45ef36674b0cf9a0c45f819b49fc480057ae759097dc
```

-	Platforms:
	-	linux; amd64

### `postgres:9.6.2-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.4 MB (14373408 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:575c5e74b7654e1da6d8e0053fb50259242929bb7953d7fdbd9fa33ef0506d25`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:12:52 GMT
ENV PG_MAJOR=9.6
# Fri, 10 Feb 2017 00:29:12 GMT
ENV PG_VERSION=9.6.2
# Fri, 10 Feb 2017 00:29:13 GMT
ENV PG_SHA256=0187b5184be1c09034e74e44761505e52357248451b0c854dddec6c231fe50c9
# Fri, 10 Feb 2017 00:33:23 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:33:24 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:33:26 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:33:27 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:33:28 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:33:29 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:33:30 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:33:31 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:33:32 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:33:33 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:33:34 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:33:35 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60067b80e18181dbba533b0c274f8aab78d48c925c268b4b207d8f9d675f3559`  
		Last Modified: Fri, 10 Feb 2017 00:55:09 GMT  
		Size: 12.5 MB (12462019 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:331054c8ce4ac57fdfb4c3ee349d2f794878be42ace77b3cf2dc100a728027a2`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 7.1 KB (7095 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4963b014ebaf1bb63100f93c218fb61d50455b862874f24863646f7adc2f4f46`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:239884a93ce702af7b54a1c91cfbd91169673a68a0be12a1a4f1c1157db0b8df`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d7c82a5487f557244d5cf4c52569664f916e234f89489a20785b0a139ccc66b`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 1.7 KB (1689 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e19b72283336ad5954492354b59c8c062e13b88a5e23664b579385542b613929`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.6-alpine`

```console
$ docker pull postgres@sha256:f501aae03fc31749599a45ef36674b0cf9a0c45f819b49fc480057ae759097dc
```

-	Platforms:
	-	linux; amd64

### `postgres:9.6-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.4 MB (14373408 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:575c5e74b7654e1da6d8e0053fb50259242929bb7953d7fdbd9fa33ef0506d25`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:12:52 GMT
ENV PG_MAJOR=9.6
# Fri, 10 Feb 2017 00:29:12 GMT
ENV PG_VERSION=9.6.2
# Fri, 10 Feb 2017 00:29:13 GMT
ENV PG_SHA256=0187b5184be1c09034e74e44761505e52357248451b0c854dddec6c231fe50c9
# Fri, 10 Feb 2017 00:33:23 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:33:24 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:33:26 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:33:27 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:33:28 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:33:29 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:33:30 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:33:31 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:33:32 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:33:33 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:33:34 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:33:35 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60067b80e18181dbba533b0c274f8aab78d48c925c268b4b207d8f9d675f3559`  
		Last Modified: Fri, 10 Feb 2017 00:55:09 GMT  
		Size: 12.5 MB (12462019 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:331054c8ce4ac57fdfb4c3ee349d2f794878be42ace77b3cf2dc100a728027a2`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 7.1 KB (7095 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4963b014ebaf1bb63100f93c218fb61d50455b862874f24863646f7adc2f4f46`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:239884a93ce702af7b54a1c91cfbd91169673a68a0be12a1a4f1c1157db0b8df`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d7c82a5487f557244d5cf4c52569664f916e234f89489a20785b0a139ccc66b`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 1.7 KB (1689 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e19b72283336ad5954492354b59c8c062e13b88a5e23664b579385542b613929`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9-alpine`

```console
$ docker pull postgres@sha256:f501aae03fc31749599a45ef36674b0cf9a0c45f819b49fc480057ae759097dc
```

-	Platforms:
	-	linux; amd64

### `postgres:9-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.4 MB (14373408 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:575c5e74b7654e1da6d8e0053fb50259242929bb7953d7fdbd9fa33ef0506d25`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:12:52 GMT
ENV PG_MAJOR=9.6
# Fri, 10 Feb 2017 00:29:12 GMT
ENV PG_VERSION=9.6.2
# Fri, 10 Feb 2017 00:29:13 GMT
ENV PG_SHA256=0187b5184be1c09034e74e44761505e52357248451b0c854dddec6c231fe50c9
# Fri, 10 Feb 2017 00:33:23 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:33:24 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:33:26 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:33:27 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:33:28 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:33:29 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:33:30 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:33:31 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:33:32 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:33:33 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:33:34 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:33:35 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60067b80e18181dbba533b0c274f8aab78d48c925c268b4b207d8f9d675f3559`  
		Last Modified: Fri, 10 Feb 2017 00:55:09 GMT  
		Size: 12.5 MB (12462019 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:331054c8ce4ac57fdfb4c3ee349d2f794878be42ace77b3cf2dc100a728027a2`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 7.1 KB (7095 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4963b014ebaf1bb63100f93c218fb61d50455b862874f24863646f7adc2f4f46`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:239884a93ce702af7b54a1c91cfbd91169673a68a0be12a1a4f1c1157db0b8df`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d7c82a5487f557244d5cf4c52569664f916e234f89489a20785b0a139ccc66b`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 1.7 KB (1689 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e19b72283336ad5954492354b59c8c062e13b88a5e23664b579385542b613929`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:alpine`

```console
$ docker pull postgres@sha256:f501aae03fc31749599a45ef36674b0cf9a0c45f819b49fc480057ae759097dc
```

-	Platforms:
	-	linux; amd64

### `postgres:alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.4 MB (14373408 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:575c5e74b7654e1da6d8e0053fb50259242929bb7953d7fdbd9fa33ef0506d25`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:12:52 GMT
ENV PG_MAJOR=9.6
# Fri, 10 Feb 2017 00:29:12 GMT
ENV PG_VERSION=9.6.2
# Fri, 10 Feb 2017 00:29:13 GMT
ENV PG_SHA256=0187b5184be1c09034e74e44761505e52357248451b0c854dddec6c231fe50c9
# Fri, 10 Feb 2017 00:33:23 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:33:24 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:33:26 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:33:27 GMT
ENV PATH=/usr/lib/postgresql/9.6/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:33:28 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:33:29 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:33:30 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:33:31 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:33:32 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:33:33 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:33:34 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:33:35 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60067b80e18181dbba533b0c274f8aab78d48c925c268b4b207d8f9d675f3559`  
		Last Modified: Fri, 10 Feb 2017 00:55:09 GMT  
		Size: 12.5 MB (12462019 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:331054c8ce4ac57fdfb4c3ee349d2f794878be42ace77b3cf2dc100a728027a2`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 7.1 KB (7095 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4963b014ebaf1bb63100f93c218fb61d50455b862874f24863646f7adc2f4f46`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:239884a93ce702af7b54a1c91cfbd91169673a68a0be12a1a4f1c1157db0b8df`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d7c82a5487f557244d5cf4c52569664f916e234f89489a20785b0a139ccc66b`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 1.7 KB (1689 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e19b72283336ad5954492354b59c8c062e13b88a5e23664b579385542b613929`  
		Last Modified: Fri, 10 Feb 2017 00:55:00 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.5.6`

```console
$ docker pull postgres@sha256:cffbfbedae9df462cecdb527fd96067dc93e4d70eaa895d54a2004d2e8ccdd52
```

-	Platforms:
	-	linux; amd64

### `postgres:9.5.6` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.3 MB (101327027 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ebbb2f3c01a6afd7755e9ef57ab118dcefa17b7894a29b819d480f6cd8bf21b4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:38:58 GMT
ENV PG_MAJOR=9.5
# Fri, 10 Feb 2017 00:33:36 GMT
ENV PG_VERSION=9.5.6-1.pgdg80+1
# Fri, 10 Feb 2017 00:33:38 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:34:30 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:34:31 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:34:32 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:34:33 GMT
ENV PATH=/usr/lib/postgresql/9.5/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:34:33 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:34:34 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:34:35 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:34:35 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:34:37 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:34:37 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:34:37 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:34:38 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:953540669b75e2d1b61e342034fe12efa6cf9b7621ee28887fb5b2cb073c3551`  
		Last Modified: Fri, 10 Feb 2017 00:56:29 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adec5c6ee2cadbfe40488e7ded588797765ba3b0a1574eb9e363790f924bbd6b`  
		Last Modified: Fri, 10 Feb 2017 00:56:48 GMT  
		Size: 41.9 MB (41868569 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:930d4b52ca40ef05ef7d286e7f5ebbb124489a53029581fa39e9140c07b0a62e`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 6.9 KB (6859 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:047b7af69f97f574f8d6d965130cb2caf80bdae4b84a64b198aacfae1818a8af`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c15ce6ecfb83064b7b79aac8f90ae0a4d5db80e35285169b102f625889449bbf`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db3c8f623fc25933d83515027aa73375bf74f9d9487e072108ea536dd73da48`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 1.7 KB (1693 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2eae100cbf9302563b7cc4c461b523a54bfa2dda6f46d6cf4aa065353f46b44`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.5`

```console
$ docker pull postgres@sha256:cffbfbedae9df462cecdb527fd96067dc93e4d70eaa895d54a2004d2e8ccdd52
```

-	Platforms:
	-	linux; amd64

### `postgres:9.5` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **101.3 MB (101327027 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ebbb2f3c01a6afd7755e9ef57ab118dcefa17b7894a29b819d480f6cd8bf21b4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:38:58 GMT
ENV PG_MAJOR=9.5
# Fri, 10 Feb 2017 00:33:36 GMT
ENV PG_VERSION=9.5.6-1.pgdg80+1
# Fri, 10 Feb 2017 00:33:38 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:34:30 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:34:31 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:34:32 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:34:33 GMT
ENV PATH=/usr/lib/postgresql/9.5/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:34:33 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:34:34 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:34:35 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:34:35 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:34:37 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:34:37 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:34:37 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:34:38 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:953540669b75e2d1b61e342034fe12efa6cf9b7621ee28887fb5b2cb073c3551`  
		Last Modified: Fri, 10 Feb 2017 00:56:29 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adec5c6ee2cadbfe40488e7ded588797765ba3b0a1574eb9e363790f924bbd6b`  
		Last Modified: Fri, 10 Feb 2017 00:56:48 GMT  
		Size: 41.9 MB (41868569 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:930d4b52ca40ef05ef7d286e7f5ebbb124489a53029581fa39e9140c07b0a62e`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 6.9 KB (6859 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:047b7af69f97f574f8d6d965130cb2caf80bdae4b84a64b198aacfae1818a8af`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c15ce6ecfb83064b7b79aac8f90ae0a4d5db80e35285169b102f625889449bbf`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db3c8f623fc25933d83515027aa73375bf74f9d9487e072108ea536dd73da48`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 1.7 KB (1693 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2eae100cbf9302563b7cc4c461b523a54bfa2dda6f46d6cf4aa065353f46b44`  
		Last Modified: Fri, 10 Feb 2017 00:56:27 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.5.6-alpine`

```console
$ docker pull postgres@sha256:d0b99f91d43d9e3e6e1530ad2c988b0ad3e4caa70f021650854a15036df8ea26
```

-	Platforms:
	-	linux; amd64

### `postgres:9.5.6-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.1 MB (14093406 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c6968dc5efdaf70bc764c32e0713a8747863a115d4fcfe1e05357c2c3bc89e5a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:15:09 GMT
ENV PG_MAJOR=9.5
# Fri, 10 Feb 2017 00:34:39 GMT
ENV PG_VERSION=9.5.6
# Fri, 10 Feb 2017 00:34:39 GMT
ENV PG_SHA256=bb9e5f6d34e20783e96e10c1d6c0c09c31749e802aaa46b793ce2522725ae12f
# Fri, 10 Feb 2017 00:38:37 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:38:39 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:38:40 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:38:40 GMT
ENV PATH=/usr/lib/postgresql/9.5/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:38:40 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:38:42 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:38:42 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:38:43 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:38:44 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:38:44 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:38:45 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:38:45 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:000242e19acb45f869ba237ef48d377b211708e3fd55c621b15b723f9091a06c`  
		Last Modified: Fri, 10 Feb 2017 00:57:39 GMT  
		Size: 12.2 MB (12182290 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18bb249f84ea00f0a219795f102e1360aa14f74a65c8c5e30be3efa116ab1c10`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 6.8 KB (6826 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f7665bfe787b3554ea676c6e6ddde1ba47b7bcff59e628ee03538d9b8c2243ba`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09facd325886b12b34082a6ae3ae25337b2887813edd0dd50eedb4e8b7548bd4`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85e0517c36d20397e0f165faa1ea3e38151e42a0b0057db50f542c9455ed2bd0`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 1.7 KB (1685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:407d08e3e677c658dc51ef8efed7e7cf7e3a0f568b2f0ce9d57c47a8d2762260`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.5-alpine`

```console
$ docker pull postgres@sha256:d0b99f91d43d9e3e6e1530ad2c988b0ad3e4caa70f021650854a15036df8ea26
```

-	Platforms:
	-	linux; amd64

### `postgres:9.5-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.1 MB (14093406 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c6968dc5efdaf70bc764c32e0713a8747863a115d4fcfe1e05357c2c3bc89e5a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:15:09 GMT
ENV PG_MAJOR=9.5
# Fri, 10 Feb 2017 00:34:39 GMT
ENV PG_VERSION=9.5.6
# Fri, 10 Feb 2017 00:34:39 GMT
ENV PG_SHA256=bb9e5f6d34e20783e96e10c1d6c0c09c31749e802aaa46b793ce2522725ae12f
# Fri, 10 Feb 2017 00:38:37 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:38:39 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:38:40 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:38:40 GMT
ENV PATH=/usr/lib/postgresql/9.5/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:38:40 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:38:42 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:38:42 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:38:43 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:38:44 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:38:44 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:38:45 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:38:45 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:000242e19acb45f869ba237ef48d377b211708e3fd55c621b15b723f9091a06c`  
		Last Modified: Fri, 10 Feb 2017 00:57:39 GMT  
		Size: 12.2 MB (12182290 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18bb249f84ea00f0a219795f102e1360aa14f74a65c8c5e30be3efa116ab1c10`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 6.8 KB (6826 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f7665bfe787b3554ea676c6e6ddde1ba47b7bcff59e628ee03538d9b8c2243ba`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09facd325886b12b34082a6ae3ae25337b2887813edd0dd50eedb4e8b7548bd4`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85e0517c36d20397e0f165faa1ea3e38151e42a0b0057db50f542c9455ed2bd0`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 1.7 KB (1685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:407d08e3e677c658dc51ef8efed7e7cf7e3a0f568b2f0ce9d57c47a8d2762260`  
		Last Modified: Fri, 10 Feb 2017 00:57:31 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.4.11`

```console
$ docker pull postgres@sha256:c681c72ff62b637b9ad3806a946f14450f74ee0888ca70ec1472a4e0552054c2
```

-	Platforms:
	-	linux; amd64

### `postgres:9.4.11` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **100.9 MB (100914022 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5878c998b6b583f3cd9c44bc649bd3096a18df4041dc07dd1070eeafc2a048ad`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:38:20 GMT
ENV PG_MAJOR=9.4
# Fri, 10 Feb 2017 00:38:46 GMT
ENV PG_VERSION=9.4.11-1.pgdg80+1
# Fri, 10 Feb 2017 00:38:47 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:39:29 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:39:30 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:39:31 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:39:32 GMT
ENV PATH=/usr/lib/postgresql/9.4/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:39:32 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:39:33 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:39:34 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:39:34 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:39:35 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:39:36 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:39:36 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:39:37 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76d12bfb9a68dd8e92c967f144044d0f08d460760fe2fab84f70ed3a3920665a`  
		Last Modified: Fri, 10 Feb 2017 00:58:22 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6cc4865c8c3536b8f685705853ace379705b233c0785b972a96afefda4acac76`  
		Last Modified: Fri, 10 Feb 2017 00:58:39 GMT  
		Size: 41.5 MB (41455711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37dde1aef6982b702d2bb2536555d250a89481aaae0f6497d984a4accd63c4c2`  
		Last Modified: Fri, 10 Feb 2017 00:58:21 GMT  
		Size: 6.7 KB (6711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14c5bb3a37217aa988542c984fa50ab3b867495dd3ef288532af2ad5edf58ec8`  
		Last Modified: Fri, 10 Feb 2017 00:58:20 GMT  
		Size: 135.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ea50576a1d9fef2e6305254ee2b045478c26fc27e6b9a9f03903f4079fbe580`  
		Last Modified: Fri, 10 Feb 2017 00:58:20 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3efbbe19e8726bb1b86e5de5d8cedb70d4aeba8113140bc6a575d7369447e69`  
		Last Modified: Fri, 10 Feb 2017 00:58:20 GMT  
		Size: 1.7 KB (1691 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b7fe7b5738819e2a0554e383771c9f37eb4ded13470650cf0f7c01b3264cee6`  
		Last Modified: Fri, 10 Feb 2017 00:58:20 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.4`

```console
$ docker pull postgres@sha256:c681c72ff62b637b9ad3806a946f14450f74ee0888ca70ec1472a4e0552054c2
```

-	Platforms:
	-	linux; amd64

### `postgres:9.4` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **100.9 MB (100914022 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5878c998b6b583f3cd9c44bc649bd3096a18df4041dc07dd1070eeafc2a048ad`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:38:20 GMT
ENV PG_MAJOR=9.4
# Fri, 10 Feb 2017 00:38:46 GMT
ENV PG_VERSION=9.4.11-1.pgdg80+1
# Fri, 10 Feb 2017 00:38:47 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:39:29 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:39:30 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:39:31 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:39:32 GMT
ENV PATH=/usr/lib/postgresql/9.4/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:39:32 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:39:33 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:39:34 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:39:34 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:39:35 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:39:36 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:39:36 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:39:37 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76d12bfb9a68dd8e92c967f144044d0f08d460760fe2fab84f70ed3a3920665a`  
		Last Modified: Fri, 10 Feb 2017 00:58:22 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6cc4865c8c3536b8f685705853ace379705b233c0785b972a96afefda4acac76`  
		Last Modified: Fri, 10 Feb 2017 00:58:39 GMT  
		Size: 41.5 MB (41455711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37dde1aef6982b702d2bb2536555d250a89481aaae0f6497d984a4accd63c4c2`  
		Last Modified: Fri, 10 Feb 2017 00:58:21 GMT  
		Size: 6.7 KB (6711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14c5bb3a37217aa988542c984fa50ab3b867495dd3ef288532af2ad5edf58ec8`  
		Last Modified: Fri, 10 Feb 2017 00:58:20 GMT  
		Size: 135.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ea50576a1d9fef2e6305254ee2b045478c26fc27e6b9a9f03903f4079fbe580`  
		Last Modified: Fri, 10 Feb 2017 00:58:20 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3efbbe19e8726bb1b86e5de5d8cedb70d4aeba8113140bc6a575d7369447e69`  
		Last Modified: Fri, 10 Feb 2017 00:58:20 GMT  
		Size: 1.7 KB (1691 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b7fe7b5738819e2a0554e383771c9f37eb4ded13470650cf0f7c01b3264cee6`  
		Last Modified: Fri, 10 Feb 2017 00:58:20 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.4.11-alpine`

```console
$ docker pull postgres@sha256:71f8e6b24c9f692c2f1d8ba0dac4aff1cfcf68241b545565e362a61065c8e1da
```

-	Platforms:
	-	linux; amd64

### `postgres:9.4.11-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.9 MB (13875510 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9155c4b9f5eb3ee9233ccdb1819dbba3d509906ef366167a9083338b31c94a2f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:17:16 GMT
ENV PG_MAJOR=9.4
# Fri, 10 Feb 2017 00:39:37 GMT
ENV PG_VERSION=9.4.11
# Fri, 10 Feb 2017 00:39:38 GMT
ENV PG_SHA256=e3eb51d045c180b03d2de1f0c3af9356e10be49448e966ca01dfc2c6d1cc9d23
# Fri, 10 Feb 2017 00:43:21 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:43:23 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:43:24 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:43:24 GMT
ENV PATH=/usr/lib/postgresql/9.4/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:43:25 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:43:26 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:43:26 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:43:27 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:43:28 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:43:28 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:43:29 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:43:29 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4e54f4d7d906f1e8393c83cb88a400d176a34e0804874b78b338e01d480015f`  
		Last Modified: Fri, 10 Feb 2017 00:59:29 GMT  
		Size: 12.0 MB (11964542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7755ce214a0e72e4ebae6f3ac872080823a75d19d9f729006a3bb24c92b0c2f3`  
		Last Modified: Fri, 10 Feb 2017 00:59:22 GMT  
		Size: 6.7 KB (6678 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf80223e87938ddeb464b65c6081086f785db1bc27fa2c0d19e7b2687d993270`  
		Last Modified: Fri, 10 Feb 2017 00:59:21 GMT  
		Size: 144.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef3a5319940fb0dfa5734a2a50a1a9b69a4536bf5cbb26d370b568a6a3bde3e9`  
		Last Modified: Fri, 10 Feb 2017 00:59:21 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1712c9622f999cd049e16ae6a62b900e8827ac4cac7aeb4b2445b67cc0180dd0`  
		Last Modified: Fri, 10 Feb 2017 00:59:21 GMT  
		Size: 1.7 KB (1686 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5df77c066285d1354b7da8927a416cde916ad09557b45a185a5b581d4d71f03`  
		Last Modified: Fri, 10 Feb 2017 00:59:21 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.4-alpine`

```console
$ docker pull postgres@sha256:71f8e6b24c9f692c2f1d8ba0dac4aff1cfcf68241b545565e362a61065c8e1da
```

-	Platforms:
	-	linux; amd64

### `postgres:9.4-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.9 MB (13875510 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9155c4b9f5eb3ee9233ccdb1819dbba3d509906ef366167a9083338b31c94a2f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:17:16 GMT
ENV PG_MAJOR=9.4
# Fri, 10 Feb 2017 00:39:37 GMT
ENV PG_VERSION=9.4.11
# Fri, 10 Feb 2017 00:39:38 GMT
ENV PG_SHA256=e3eb51d045c180b03d2de1f0c3af9356e10be49448e966ca01dfc2c6d1cc9d23
# Fri, 10 Feb 2017 00:43:21 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:43:23 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:43:24 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:43:24 GMT
ENV PATH=/usr/lib/postgresql/9.4/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:43:25 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:43:26 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:43:26 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:43:27 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:43:28 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:43:28 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:43:29 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:43:29 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4e54f4d7d906f1e8393c83cb88a400d176a34e0804874b78b338e01d480015f`  
		Last Modified: Fri, 10 Feb 2017 00:59:29 GMT  
		Size: 12.0 MB (11964542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7755ce214a0e72e4ebae6f3ac872080823a75d19d9f729006a3bb24c92b0c2f3`  
		Last Modified: Fri, 10 Feb 2017 00:59:22 GMT  
		Size: 6.7 KB (6678 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf80223e87938ddeb464b65c6081086f785db1bc27fa2c0d19e7b2687d993270`  
		Last Modified: Fri, 10 Feb 2017 00:59:21 GMT  
		Size: 144.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef3a5319940fb0dfa5734a2a50a1a9b69a4536bf5cbb26d370b568a6a3bde3e9`  
		Last Modified: Fri, 10 Feb 2017 00:59:21 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1712c9622f999cd049e16ae6a62b900e8827ac4cac7aeb4b2445b67cc0180dd0`  
		Last Modified: Fri, 10 Feb 2017 00:59:21 GMT  
		Size: 1.7 KB (1686 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5df77c066285d1354b7da8927a416cde916ad09557b45a185a5b581d4d71f03`  
		Last Modified: Fri, 10 Feb 2017 00:59:21 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.3.16`

```console
$ docker pull postgres@sha256:f26cf5fed8669866c9f42a759e91b26e1ce9e1277b508e7adebe74c21b3b7b0a
```

-	Platforms:
	-	linux; amd64

### `postgres:9.3.16` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **100.6 MB (100563437 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0dac9586c27450ae6f0e524b3a1d419c9774077a5afd6be32268b2e4dbeb2925`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:37:44 GMT
ENV PG_MAJOR=9.3
# Fri, 10 Feb 2017 00:43:30 GMT
ENV PG_VERSION=9.3.16-1.pgdg80+1
# Fri, 10 Feb 2017 00:43:31 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:44:16 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:44:17 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:44:18 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:44:19 GMT
ENV PATH=/usr/lib/postgresql/9.3/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:44:19 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:44:20 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:44:21 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:44:21 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:44:23 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:44:23 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:44:23 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:44:24 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f04b28c83e0fe30607805831806ef926029ea142e45353ddec12fc528f0d47ef`  
		Last Modified: Fri, 10 Feb 2017 01:00:14 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89e4954c61ecdc5b36afa91f912653a0bc1bfd84b09597dae4378b352e88f08d`  
		Last Modified: Fri, 10 Feb 2017 01:00:32 GMT  
		Size: 41.1 MB (41105311 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3767968f3a437e6a303d8e57e5faae7480be62b6df748b8240e7ae239730dec1`  
		Last Modified: Fri, 10 Feb 2017 01:00:12 GMT  
		Size: 6.5 KB (6528 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:811e50847f2a5e34c76e5a95b590999dfa78af78ebc5f680c6064c1192ea99a5`  
		Last Modified: Fri, 10 Feb 2017 01:00:12 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a0ff6545721dbb771eca6c9f8ced3283f52a5b88a624a18a03e0aa1d0b30429`  
		Last Modified: Fri, 10 Feb 2017 01:00:14 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd839b60878d2c4678e357fe8ab5444c1e26d56b69cbec37fa3b93582f2db5b7`  
		Last Modified: Fri, 10 Feb 2017 01:00:12 GMT  
		Size: 1.7 KB (1690 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5ca70200271533290557b4f9fa5d491fe67a03016e59cd25dada361624efa4a`  
		Last Modified: Fri, 10 Feb 2017 01:00:12 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.3`

```console
$ docker pull postgres@sha256:f26cf5fed8669866c9f42a759e91b26e1ce9e1277b508e7adebe74c21b3b7b0a
```

-	Platforms:
	-	linux; amd64

### `postgres:9.3` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **100.6 MB (100563437 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0dac9586c27450ae6f0e524b3a1d419c9774077a5afd6be32268b2e4dbeb2925`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:37:44 GMT
ENV PG_MAJOR=9.3
# Fri, 10 Feb 2017 00:43:30 GMT
ENV PG_VERSION=9.3.16-1.pgdg80+1
# Fri, 10 Feb 2017 00:43:31 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:44:16 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:44:17 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:44:18 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:44:19 GMT
ENV PATH=/usr/lib/postgresql/9.3/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:44:19 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:44:20 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:44:21 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:44:21 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:44:23 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:44:23 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:44:23 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:44:24 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f04b28c83e0fe30607805831806ef926029ea142e45353ddec12fc528f0d47ef`  
		Last Modified: Fri, 10 Feb 2017 01:00:14 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89e4954c61ecdc5b36afa91f912653a0bc1bfd84b09597dae4378b352e88f08d`  
		Last Modified: Fri, 10 Feb 2017 01:00:32 GMT  
		Size: 41.1 MB (41105311 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3767968f3a437e6a303d8e57e5faae7480be62b6df748b8240e7ae239730dec1`  
		Last Modified: Fri, 10 Feb 2017 01:00:12 GMT  
		Size: 6.5 KB (6528 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:811e50847f2a5e34c76e5a95b590999dfa78af78ebc5f680c6064c1192ea99a5`  
		Last Modified: Fri, 10 Feb 2017 01:00:12 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a0ff6545721dbb771eca6c9f8ced3283f52a5b88a624a18a03e0aa1d0b30429`  
		Last Modified: Fri, 10 Feb 2017 01:00:14 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd839b60878d2c4678e357fe8ab5444c1e26d56b69cbec37fa3b93582f2db5b7`  
		Last Modified: Fri, 10 Feb 2017 01:00:12 GMT  
		Size: 1.7 KB (1690 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5ca70200271533290557b4f9fa5d491fe67a03016e59cd25dada361624efa4a`  
		Last Modified: Fri, 10 Feb 2017 01:00:12 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.3.16-alpine`

```console
$ docker pull postgres@sha256:df8c171e50f08f5d12a57a62dad60bf16007611f0bd8a93559c20e3044e19075
```

-	Platforms:
	-	linux; amd64

### `postgres:9.3.16-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.6 MB (13561206 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a24edece8ecdffa29a56abcfed522cbbd241d69de298c46ec2a53c0ebf0f562a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:19:17 GMT
ENV PG_MAJOR=9.3
# Fri, 10 Feb 2017 00:44:25 GMT
ENV PG_VERSION=9.3.16
# Fri, 10 Feb 2017 00:44:25 GMT
ENV PG_SHA256=845f5e4ac8cf026b6a77c5a180a2fe869f51e9d06acf8d0365b05505a2c66873
# Fri, 10 Feb 2017 00:48:02 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:48:03 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:48:05 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:48:05 GMT
ENV PATH=/usr/lib/postgresql/9.3/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:48:05 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:48:07 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:48:07 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:48:08 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:48:09 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:48:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:48:10 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:48:10 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23ec93d82176c35f3f75b40c9aa53b1131ca833a4c670ea32d39bc69961acc2b`  
		Last Modified: Fri, 10 Feb 2017 01:01:29 GMT  
		Size: 11.7 MB (11650419 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d5e3cb9e7b2f865a3aa1d2b89f87adc61f1038af80741f42aed558f1c51fa61`  
		Last Modified: Fri, 10 Feb 2017 01:01:20 GMT  
		Size: 6.5 KB (6500 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dabd8f2b2d486a3f44fae2038c316c62bafd21b01e81e04e9f8c9904b8665d6d`  
		Last Modified: Fri, 10 Feb 2017 01:01:20 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:58a43d833d9d29323c2cf068a3bb12f422a094bd498b881f4de30d8024be7cd4`  
		Last Modified: Fri, 10 Feb 2017 01:01:22 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3a1a0c6f91d7377fd80763027cfea7274e04c809831d4f679a8ed2ab5b8bcb6`  
		Last Modified: Fri, 10 Feb 2017 01:01:20 GMT  
		Size: 1.7 KB (1683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ecbc1cbdb74173255f382c94d14c14f7e26c91d739424131a8f8171c1a1002a`  
		Last Modified: Fri, 10 Feb 2017 01:01:20 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.3-alpine`

```console
$ docker pull postgres@sha256:df8c171e50f08f5d12a57a62dad60bf16007611f0bd8a93559c20e3044e19075
```

-	Platforms:
	-	linux; amd64

### `postgres:9.3-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.6 MB (13561206 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a24edece8ecdffa29a56abcfed522cbbd241d69de298c46ec2a53c0ebf0f562a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:19:17 GMT
ENV PG_MAJOR=9.3
# Fri, 10 Feb 2017 00:44:25 GMT
ENV PG_VERSION=9.3.16
# Fri, 10 Feb 2017 00:44:25 GMT
ENV PG_SHA256=845f5e4ac8cf026b6a77c5a180a2fe869f51e9d06acf8d0365b05505a2c66873
# Fri, 10 Feb 2017 00:48:02 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:48:03 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:48:05 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:48:05 GMT
ENV PATH=/usr/lib/postgresql/9.3/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:48:05 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:48:07 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:48:07 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:48:08 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:48:09 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:48:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:48:10 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:48:10 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23ec93d82176c35f3f75b40c9aa53b1131ca833a4c670ea32d39bc69961acc2b`  
		Last Modified: Fri, 10 Feb 2017 01:01:29 GMT  
		Size: 11.7 MB (11650419 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d5e3cb9e7b2f865a3aa1d2b89f87adc61f1038af80741f42aed558f1c51fa61`  
		Last Modified: Fri, 10 Feb 2017 01:01:20 GMT  
		Size: 6.5 KB (6500 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dabd8f2b2d486a3f44fae2038c316c62bafd21b01e81e04e9f8c9904b8665d6d`  
		Last Modified: Fri, 10 Feb 2017 01:01:20 GMT  
		Size: 145.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:58a43d833d9d29323c2cf068a3bb12f422a094bd498b881f4de30d8024be7cd4`  
		Last Modified: Fri, 10 Feb 2017 01:01:22 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3a1a0c6f91d7377fd80763027cfea7274e04c809831d4f679a8ed2ab5b8bcb6`  
		Last Modified: Fri, 10 Feb 2017 01:01:20 GMT  
		Size: 1.7 KB (1683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ecbc1cbdb74173255f382c94d14c14f7e26c91d739424131a8f8171c1a1002a`  
		Last Modified: Fri, 10 Feb 2017 01:01:20 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.2.20`

```console
$ docker pull postgres@sha256:77f5f614520920cc1dc58295d473ce96608ae367ca36ce9f26e251cd87ce090a
```

-	Platforms:
	-	linux; amd64

### `postgres:9.2.20` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **100.4 MB (100397553 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c2593c7fff04d9065031af41a18aff2581a66781671a4dcc2f3826428d82a491`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:37:06 GMT
ENV PG_MAJOR=9.2
# Fri, 10 Feb 2017 00:48:11 GMT
ENV PG_VERSION=9.2.20-1.pgdg80+1
# Fri, 10 Feb 2017 00:48:12 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:48:54 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:48:56 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:48:57 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:48:57 GMT
ENV PATH=/usr/lib/postgresql/9.2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:48:58 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:48:59 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:49:00 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:49:00 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:49:02 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:49:02 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:49:02 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:49:03 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:356ae9126cc8e4fec97f664a8200b7c2f0b51214844ff043edb2a9c431f89b73`  
		Last Modified: Fri, 10 Feb 2017 01:02:12 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49197561a66bf3308955fc1c978cafbbcca2fbfe0db4b6f7dd55569dcf14b366`  
		Last Modified: Fri, 10 Feb 2017 01:02:31 GMT  
		Size: 40.9 MB (40939483 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7b21a3ef9dfcfa1897362cbd39b8b906b01223db3237f9cfd73578e0f9195fe`  
		Last Modified: Fri, 10 Feb 2017 01:02:10 GMT  
		Size: 6.5 KB (6472 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dccee6387230dcc8ed944bc82c92ed109d6d5f22bca3b7f7c746ac78b2d6ecf4`  
		Last Modified: Fri, 10 Feb 2017 01:02:11 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f1955b4305d16086ec4b092205e28989d1a7ce9baa434ce87a6e82a3f44e2c6`  
		Last Modified: Fri, 10 Feb 2017 01:02:10 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f06ef0f98165082b6a8b0a4ab40c639b1b0161d53aa6ddfe7799af4245d7270`  
		Last Modified: Fri, 10 Feb 2017 01:02:10 GMT  
		Size: 1.7 KB (1691 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:954bf85c454cdfc3b6ffe872787b59698463be6012635b99a8009fc6ccd0a937`  
		Last Modified: Fri, 10 Feb 2017 01:02:10 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.2`

```console
$ docker pull postgres@sha256:77f5f614520920cc1dc58295d473ce96608ae367ca36ce9f26e251cd87ce090a
```

-	Platforms:
	-	linux; amd64

### `postgres:9.2` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **100.4 MB (100397553 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c2593c7fff04d9065031af41a18aff2581a66781671a4dcc2f3826428d82a491`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 19:36:05 GMT
RUN groupadd -r postgres --gid=999 && useradd -r -g postgres --uid=999 postgres
# Tue, 17 Jan 2017 19:36:05 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 19:36:20 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 17 Jan 2017 19:36:27 GMT
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* 	&& localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
# Tue, 17 Jan 2017 19:36:27 GMT
ENV LANG=en_US.utf8
# Tue, 17 Jan 2017 19:36:28 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 17 Jan 2017 19:36:30 GMT
RUN set -ex; 	key='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/postgres.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 19:37:06 GMT
ENV PG_MAJOR=9.2
# Fri, 10 Feb 2017 00:48:11 GMT
ENV PG_VERSION=9.2.20-1.pgdg80+1
# Fri, 10 Feb 2017 00:48:12 GMT
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ jessie-pgdg main' $PG_MAJOR > /etc/apt/sources.list.d/pgdg.list
# Fri, 10 Feb 2017 00:48:54 GMT
RUN apt-get update 	&& apt-get install -y postgresql-common 	&& sed -ri 's/#(create_main_cluster) .*$/\1 = false/' /etc/postgresql-common/createcluster.conf 	&& apt-get install -y 		postgresql-$PG_MAJOR=$PG_VERSION 		postgresql-contrib-$PG_MAJOR=$PG_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Fri, 10 Feb 2017 00:48:56 GMT
RUN mv -v /usr/share/postgresql/$PG_MAJOR/postgresql.conf.sample /usr/share/postgresql/ 	&& ln -sv ../postgresql.conf.sample /usr/share/postgresql/$PG_MAJOR/ 	&& sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:48:57 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:48:57 GMT
ENV PATH=/usr/lib/postgresql/9.2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:48:58 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:48:59 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:49:00 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:49:00 GMT
COPY file:8d267d76d9551f01f3b15b68c484da091c34fd675a9b6adc8c279d52364efdfc in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:49:02 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:49:02 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:49:02 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:49:03 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f08454c3c700a0100e8c3424e7048c4160e48c03bf045eada703f69fae65a3f2`  
		Last Modified: Wed, 18 Jan 2017 06:53:25 GMT  
		Size: 2.0 KB (2041 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4db038cdfe0347fab843472aa89d5b85a99a77dac608e5b91962eebcf6a8d1da`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 1.2 MB (1216697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e1d9ba315f03586d7698b3e6157539dc65c58c4af524a5570506d954eee51a49`  
		Last Modified: Wed, 18 Jan 2017 06:53:26 GMT  
		Size: 6.9 MB (6865805 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e0ee93170ea48b465208dd9a5b66c43359df595268299d92caed4ed36f59be`  
		Last Modified: Wed, 18 Jan 2017 06:53:23 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f28084c3f5120489e6a0d65a6838996fd8ef9f688ad92024b2e01d8955273c5`  
		Last Modified: Wed, 18 Jan 2017 06:53:22 GMT  
		Size: 3.4 KB (3400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:356ae9126cc8e4fec97f664a8200b7c2f0b51214844ff043edb2a9c431f89b73`  
		Last Modified: Fri, 10 Feb 2017 01:02:12 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49197561a66bf3308955fc1c978cafbbcca2fbfe0db4b6f7dd55569dcf14b366`  
		Last Modified: Fri, 10 Feb 2017 01:02:31 GMT  
		Size: 40.9 MB (40939483 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7b21a3ef9dfcfa1897362cbd39b8b906b01223db3237f9cfd73578e0f9195fe`  
		Last Modified: Fri, 10 Feb 2017 01:02:10 GMT  
		Size: 6.5 KB (6472 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dccee6387230dcc8ed944bc82c92ed109d6d5f22bca3b7f7c746ac78b2d6ecf4`  
		Last Modified: Fri, 10 Feb 2017 01:02:11 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f1955b4305d16086ec4b092205e28989d1a7ce9baa434ce87a6e82a3f44e2c6`  
		Last Modified: Fri, 10 Feb 2017 01:02:10 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f06ef0f98165082b6a8b0a4ab40c639b1b0161d53aa6ddfe7799af4245d7270`  
		Last Modified: Fri, 10 Feb 2017 01:02:10 GMT  
		Size: 1.7 KB (1691 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:954bf85c454cdfc3b6ffe872787b59698463be6012635b99a8009fc6ccd0a937`  
		Last Modified: Fri, 10 Feb 2017 01:02:10 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.2.20-alpine`

```console
$ docker pull postgres@sha256:ea46a36be71a1c22a1c1e19d7fae708d78a5250cb889f53d8522f2dd27d00178
```

-	Platforms:
	-	linux; amd64

### `postgres:9.2.20-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.4 MB (13399270 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:76e59f83af3dccab7a4fee8b0dd71e3f836b1b33a9f6444d7a46b63ec1a53ad4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:21:14 GMT
ENV PG_MAJOR=9.2
# Fri, 10 Feb 2017 00:49:04 GMT
ENV PG_VERSION=9.2.20
# Fri, 10 Feb 2017 00:49:04 GMT
ENV PG_SHA256=0b8abdae8400cabea5587a726003c9dd71c73c049bdae523abc35f9312dd8f26
# Fri, 10 Feb 2017 00:52:37 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:52:38 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:52:39 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:52:40 GMT
ENV PATH=/usr/lib/postgresql/9.2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:52:40 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:52:41 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:52:41 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:52:42 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:52:43 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:52:44 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:52:44 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:52:44 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e499b936de3a4149007f2dd12c22a03c5c75ff6ed215d7ad0f59d42d6b302303`  
		Last Modified: Fri, 10 Feb 2017 01:03:23 GMT  
		Size: 11.5 MB (11488541 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a2d94ae7f36061759814a17e2550d64edd78676c3b2d1130428ac76819010273`  
		Last Modified: Fri, 10 Feb 2017 01:03:14 GMT  
		Size: 6.4 KB (6441 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61ae45377e8b3983a2e62b7d8cb1cace859c170c532a36ea5cdcb32284679e0c`  
		Last Modified: Fri, 10 Feb 2017 01:03:14 GMT  
		Size: 144.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fbd9ea2b621d1f0a7630e008f3af6f1061f84c94cd1f484538a336d12aa1c8e`  
		Last Modified: Fri, 10 Feb 2017 01:03:15 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:83ed19c823bda5e150d7d78f0f9151d381a583b2929a042e76bfaae1fefa3b86`  
		Last Modified: Fri, 10 Feb 2017 01:03:14 GMT  
		Size: 1.7 KB (1685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5cedd960abd791665fa492c6f1f950c7d963867d00f4b5a1badef690eb06c7ae`  
		Last Modified: Fri, 10 Feb 2017 01:03:15 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `postgres:9.2-alpine`

```console
$ docker pull postgres@sha256:ea46a36be71a1c22a1c1e19d7fae708d78a5250cb889f53d8522f2dd27d00178
```

-	Platforms:
	-	linux; amd64

### `postgres:9.2-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.4 MB (13399270 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:76e59f83af3dccab7a4fee8b0dd71e3f836b1b33a9f6444d7a46b63ec1a53ad4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["postgres"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:12:51 GMT
ENV LANG=en_US.utf8
# Wed, 04 Jan 2017 21:12:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 04 Jan 2017 21:21:14 GMT
ENV PG_MAJOR=9.2
# Fri, 10 Feb 2017 00:49:04 GMT
ENV PG_VERSION=9.2.20
# Fri, 10 Feb 2017 00:49:04 GMT
ENV PG_SHA256=0b8abdae8400cabea5587a726003c9dd71c73c049bdae523abc35f9312dd8f26
# Fri, 10 Feb 2017 00:52:37 GMT
RUN set -ex 		&& apk add --no-cache --virtual .fetch-deps 		ca-certificates 		openssl 		tar 		&& wget -O postgresql.tar.bz2 "https://ftp.postgresql.org/pub/source/v$PG_VERSION/postgresql-$PG_VERSION.tar.bz2" 	&& echo "$PG_SHA256 *postgresql.tar.bz2" | sha256sum -c - 	&& mkdir -p /usr/src/postgresql 	&& tar 		--extract 		--file postgresql.tar.bz2 		--directory /usr/src/postgresql 		--strip-components 1 	&& rm postgresql.tar.bz2 		&& apk add --no-cache --virtual .build-deps 		bison 		flex 		gcc 		libc-dev 		libedit-dev 		libxml2-dev 		libxslt-dev 		make 		openssl-dev 		perl 		util-linux-dev 		zlib-dev 		&& cd /usr/src/postgresql 	&& awk '$1 == "#define" && $2 == "DEFAULT_PGSOCKET_DIR" && $3 == "\"/tmp\"" { $3 = "\"/var/run/postgresql\""; print; next } { print }' src/include/pg_config_manual.h > src/include/pg_config_manual.h.new 	&& grep '/var/run/postgresql' src/include/pg_config_manual.h.new 	&& mv src/include/pg_config_manual.h.new src/include/pg_config_manual.h 	&& ./configure 		--enable-integer-datetimes 		--enable-thread-safety 		--enable-tap-tests 		--disable-rpath 		--with-uuid=e2fs 		--with-gnu-ld 		--with-pgport=5432 		--with-system-tzdata=/usr/share/zoneinfo 		--prefix=/usr/local 				--with-openssl 		--with-libxml 		--with-libxslt 	&& make -j "$(getconf _NPROCESSORS_ONLN)" world 	&& make install-world 	&& make -C contrib install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .postgresql-rundeps 		$runDeps 		bash 		su-exec 		tzdata 	&& apk del .fetch-deps .build-deps 	&& cd / 	&& rm -rf 		/usr/src/postgresql 		/usr/local/share/doc 		/usr/local/share/man 	&& find /usr/local -name '*.a' -delete
# Fri, 10 Feb 2017 00:52:38 GMT
RUN sed -ri "s!^#?(listen_addresses)\s*=\s*\S+.*!\1 = '*'!" /usr/local/share/postgresql/postgresql.conf.sample
# Fri, 10 Feb 2017 00:52:39 GMT
RUN mkdir -p /var/run/postgresql && chown -R postgres:postgres /var/run/postgresql && chmod g+s /var/run/postgresql
# Fri, 10 Feb 2017 00:52:40 GMT
ENV PATH=/usr/lib/postgresql/9.2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 10 Feb 2017 00:52:40 GMT
ENV PGDATA=/var/lib/postgresql/data
# Fri, 10 Feb 2017 00:52:41 GMT
RUN mkdir -p "$PGDATA" && chown -R postgres:postgres "$PGDATA" && chmod 777 "$PGDATA" # this 777 will be replaced by 700 at runtime (allows semi-arbitrary "--user" values)
# Fri, 10 Feb 2017 00:52:41 GMT
VOLUME [/var/lib/postgresql/data]
# Fri, 10 Feb 2017 00:52:42 GMT
COPY file:f9a2410e9ac1ac1f8eaaa7097935e1bc01697a3aea28753ca0ff43bcb928e743 in /usr/local/bin/ 
# Fri, 10 Feb 2017 00:52:43 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 10 Feb 2017 00:52:44 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 10 Feb 2017 00:52:44 GMT
EXPOSE 5432/tcp
# Fri, 10 Feb 2017 00:52:44 GMT
CMD ["postgres"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6475055d17e005d634c9d02e63e4154e7c4435a6437afa80bef303e6c6efb7d`  
		Last Modified: Thu, 05 Jan 2017 00:25:52 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e499b936de3a4149007f2dd12c22a03c5c75ff6ed215d7ad0f59d42d6b302303`  
		Last Modified: Fri, 10 Feb 2017 01:03:23 GMT  
		Size: 11.5 MB (11488541 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a2d94ae7f36061759814a17e2550d64edd78676c3b2d1130428ac76819010273`  
		Last Modified: Fri, 10 Feb 2017 01:03:14 GMT  
		Size: 6.4 KB (6441 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61ae45377e8b3983a2e62b7d8cb1cace859c170c532a36ea5cdcb32284679e0c`  
		Last Modified: Fri, 10 Feb 2017 01:03:14 GMT  
		Size: 144.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fbd9ea2b621d1f0a7630e008f3af6f1061f84c94cd1f484538a336d12aa1c8e`  
		Last Modified: Fri, 10 Feb 2017 01:03:15 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:83ed19c823bda5e150d7d78f0f9151d381a583b2929a042e76bfaae1fefa3b86`  
		Last Modified: Fri, 10 Feb 2017 01:03:14 GMT  
		Size: 1.7 KB (1685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5cedd960abd791665fa492c6f1f950c7d963867d00f4b5a1badef690eb06c7ae`  
		Last Modified: Fri, 10 Feb 2017 01:03:15 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
