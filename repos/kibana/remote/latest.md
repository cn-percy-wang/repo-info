## `kibana:latest`

```console
$ docker pull kibana@sha256:c5d76370632beddf86e0a612d77a5d67fdd83a95120b019eaefb8c9d94d824e2
```

-	Platforms:
	-	linux; amd64

### `kibana:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **112.9 MB (112861996 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0fd28da2c94ad293942bc41b549fc33f920bb14ab591001474bae8d4528f134d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["kibana"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 17:14:20 GMT
RUN groupadd -r kibana && useradd -r -m -g kibana kibana
# Tue, 17 Jan 2017 17:15:28 GMT
RUN apt-get update && apt-get install -y 		apt-transport-https 		ca-certificates 		wget 		libfontconfig 		libfreetype6 	--no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 17 Jan 2017 17:15:29 GMT
ENV GOSU_VERSION=1.7
# Tue, 17 Jan 2017 17:15:33 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Tue, 17 Jan 2017 17:15:34 GMT
ENV TINI_VERSION=v0.9.0
# Tue, 17 Jan 2017 17:15:36 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini.asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Tue, 17 Jan 2017 17:15:38 GMT
RUN set -ex; 	key='46095ACC8548582C1A2699A9D27D666CD88E42B4'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/elastic.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 17 Jan 2017 17:15:39 GMT
RUN echo 'deb https://artifacts.elastic.co/packages/5.x/apt stable main' > /etc/apt/sources.list.d/kibana.list
# Fri, 17 Feb 2017 19:17:02 GMT
ENV KIBANA_VERSION=5.2.1
# Fri, 17 Feb 2017 19:17:26 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y --no-install-recommends kibana=$KIBANA_VERSION 	&& rm -rf /var/lib/apt/lists/* 		&& sed -ri "s!^(\#\s*)?(server\.host:).*!\2 '0.0.0.0'!" /etc/kibana/kibana.yml 	&& grep -q "^server\.host: '0.0.0.0'\$" /etc/kibana/kibana.yml 		&& sed -ri "s!^(\#\s*)?(elasticsearch\.url:).*!\2 'http://elasticsearch:9200'!" /etc/kibana/kibana.yml 	&& grep -q "^elasticsearch\.url: 'http://elasticsearch:9200'\$" /etc/kibana/kibana.yml
# Fri, 17 Feb 2017 19:17:27 GMT
ENV PATH=/usr/share/kibana/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 17 Feb 2017 19:17:28 GMT
COPY file:9a3ed3a1655d5afa631fded5211f1c33f5f49f1d1e0e0d9a031c9e8601111f05 in / 
# Fri, 17 Feb 2017 19:17:29 GMT
EXPOSE 5601/tcp
# Fri, 17 Feb 2017 19:17:30 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Fri, 17 Feb 2017 19:17:30 GMT
CMD ["kibana"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ed8502e84f5ddf59d41f3b25f5ab130731fa585fa7b7d3e6be8c31740dba9cc`  
		Last Modified: Wed, 18 Jan 2017 04:23:30 GMT  
		Size: 4.3 KB (4349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90ca2be203eecc2ad84b3c10447e80d503b65cfcf83bf9666cf713c74c03bc77`  
		Last Modified: Wed, 18 Jan 2017 04:25:32 GMT  
		Size: 21.6 MB (21638331 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4cd4e8631ffa15d3d6d023ebfd37cf32a5f0476505241423df03df5f5ed71379`  
		Last Modified: Wed, 18 Jan 2017 04:25:25 GMT  
		Size: 807.9 KB (807931 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d91dad24e260c9550e1aa8212e024b781ec08039f01e98e325b1395b0a35f5d`  
		Last Modified: Wed, 18 Jan 2017 04:25:22 GMT  
		Size: 7.1 KB (7122 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e632de183972a3120decfb5ccabf6cee84b2bde5a68f479b3ef23ae0f220d793`  
		Last Modified: Wed, 18 Jan 2017 04:25:22 GMT  
		Size: 1.4 KB (1441 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d00befc3e6e4306eb767914f0ef3003129b80622e210762bdb747bf53a15bf9`  
		Last Modified: Wed, 18 Jan 2017 04:25:23 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ac4ccdc0fa24a2bc6ae445353274a2e65f9905f0d6efa3748f93bbb54b6190e6`  
		Last Modified: Fri, 17 Feb 2017 19:18:17 GMT  
		Size: 39.0 MB (39041049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67d9b739bce5166688172bf8a8937e9b1b84f05a2bb09ce6d2087a39d0440a14`  
		Last Modified: Fri, 17 Feb 2017 19:17:56 GMT  
		Size: 337.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
