## `nuxeo:LTS`

```console
$ docker pull nuxeo@sha256:919227d4532b27cf17956d766d3a59c2844dbac3e62f5bf1820b22e64c8d548e
```

-	Platforms:
	-	linux; amd64

### `nuxeo:LTS` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **711.5 MB (711506336 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6914cc2880e2a906bc939f2c6b22574a9d72afd043a847e84963d708bdf7909d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["nuxeoctl","console"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 00:00:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jan 2017 00:01:07 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jan 2017 00:49:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jan 2017 00:51:48 GMT
RUN echo 'deb http://deb.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list
# Tue, 17 Jan 2017 00:51:48 GMT
ENV LANG=C.UTF-8
# Tue, 17 Jan 2017 00:51:49 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 17 Jan 2017 00:51:49 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
# Tue, 07 Feb 2017 20:03:06 GMT
ENV JAVA_VERSION=8u121
# Tue, 07 Feb 2017 20:03:07 GMT
ENV JAVA_DEBIAN_VERSION=8u121-b13-1~bpo8+1
# Tue, 07 Feb 2017 20:03:07 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20161107~bpo8+1
# Tue, 07 Feb 2017 20:04:15 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-8-jdk="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 07 Feb 2017 20:04:17 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 07 Feb 2017 22:28:22 GMT
MAINTAINER Nuxeo <packagers@nuxeo.com>
# Tue, 07 Feb 2017 22:28:22 GMT
ENV NUXEO_USER=nuxeo
# Tue, 07 Feb 2017 22:28:24 GMT
RUN useradd -m -d /home/$NUXEO_USER -s /bin/bash $NUXEO_USER
# Tue, 07 Feb 2017 22:28:24 GMT
ENV GOSU_VERSION=1.7
# Tue, 07 Feb 2017 22:28:30 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Tue, 07 Feb 2017 22:29:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends     perl     locales     pwgen     imagemagick     ffmpeg2theora     ufraw     poppler-utils     libreoffice     libwpd-tools     exiftool     ghostscript  && rm -rf /var/lib/apt/lists/*
# Tue, 07 Feb 2017 22:29:38 GMT
ENV NUXEO_VERSION=8.10
# Tue, 07 Feb 2017 22:29:38 GMT
ENV NUXEO_MD5=29e67a19bba54099093b51d892926be1
# Tue, 07 Feb 2017 22:29:39 GMT
ENV NUXEO_HOME=/opt/nuxeo/server
# Tue, 07 Feb 2017 22:30:04 GMT
RUN curl -fsSL "http://cdn.nuxeo.com/nuxeo-${NUXEO_VERSION}/nuxeo-server-${NUXEO_VERSION}-tomcat.zip" -o /tmp/nuxeo-distribution-tomcat.zip     && echo "$NUXEO_MD5 /tmp/nuxeo-distribution-tomcat.zip" | md5sum -c -     && mkdir -p /tmp/nuxeo-distribution $(dirname $NUXEO_HOME)     && unzip -q -d /tmp/nuxeo-distribution /tmp/nuxeo-distribution-tomcat.zip     && DISTDIR=$(/bin/ls /tmp/nuxeo-distribution | head -n 1)     && mv /tmp/nuxeo-distribution/$DISTDIR $NUXEO_HOME     && sed -i -e "s/^org.nuxeo.distribution.package.*/org.nuxeo.distribution.package=docker/" $NUXEO_HOME/templates/common/config/distribution.properties     && rm -rf /tmp/nuxeo-distribution*     && chmod +x $NUXEO_HOME/bin/*ctl $NUXEO_HOME/bin/*.sh
# Tue, 07 Feb 2017 22:30:05 GMT
RUN mkdir /docker-entrypoint-initnuxeo.d
# Tue, 07 Feb 2017 22:30:06 GMT
ENV PATH=/opt/nuxeo/server/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 07 Feb 2017 22:30:07 GMT
WORKDIR /opt/nuxeo/server
# Tue, 07 Feb 2017 22:30:07 GMT
COPY file:5cebeee78434ce067bd4b8b9c42eaa20349f1a252aaf628add51d12663b04917 in / 
# Tue, 07 Feb 2017 22:30:08 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 07 Feb 2017 22:30:08 GMT
EXPOSE 8080/tcp
# Tue, 07 Feb 2017 22:30:09 GMT
EXPOSE 8787/tcp
# Tue, 07 Feb 2017 22:30:10 GMT
CMD ["nuxeoctl" "console"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fce5728aad85a763fe3c419db16885eb6f7a670a42824ea618414b8fb309ccde`  
		Last Modified: Tue, 17 Jan 2017 00:19:41 GMT  
		Size: 18.5 MB (18535441 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76610ec20bf5892e24cebd4153c7668284aa1d1151b7c3b0c7d50c579aa5ce75`  
		Last Modified: Tue, 17 Jan 2017 00:20:34 GMT  
		Size: 42.5 MB (42502406 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:60170fec2151d2108ed1420625c51138434ba4e0223d3023353d3f32ffe3cfc2`  
		Last Modified: Tue, 17 Jan 2017 21:41:40 GMT  
		Size: 593.1 KB (593146 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e98f73de8f0d2ef292f58b004d67bc6e9ee779dcfaff7ebb3964649d4787b872`  
		Last Modified: Tue, 17 Jan 2017 21:41:38 GMT  
		Size: 214.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11f7af24ed9cf47597dd6cf9963bb3e9109c963f0135e869a9e9b4999fdc12a3`  
		Last Modified: Tue, 17 Jan 2017 21:41:36 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c39ff935bbe4714f7cc9638ee005342e6c447288e9eea2ed0f59fa07558f2362`  
		Last Modified: Tue, 07 Feb 2017 20:10:58 GMT  
		Size: 130.3 MB (130315361 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e03296a7302dfafbdeffadb741ec495a2191c49ffc734a1b6366ff287bad5b5`  
		Last Modified: Tue, 07 Feb 2017 20:10:30 GMT  
		Size: 289.0 KB (289035 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65feb67bfe56d475233a5bd9c48c336f5b17b9873a7249733b2c8f62ec47cee3`  
		Last Modified: Tue, 07 Feb 2017 22:49:30 GMT  
		Size: 4.4 KB (4405 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:07329e4808a4bb58bd6e6a7aba5a9c8e25dadb6652f7dd449befead9d4766ce9`  
		Last Modified: Tue, 07 Feb 2017 22:49:29 GMT  
		Size: 807.9 KB (807927 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2634729270c866bd9763ceafccfd126c18c498ad5507f198bf1be2fdc7f1be31`  
		Last Modified: Tue, 07 Feb 2017 22:50:28 GMT  
		Size: 197.6 MB (197557795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47c9dfc6a070807d553f364f6abfbbe83f5964ca5dc1ed4aebd85145fc550d97`  
		Last Modified: Tue, 07 Feb 2017 22:49:52 GMT  
		Size: 269.5 MB (269537518 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4fc8b20454c542b789bf338d7f6c35f69f94f1d0487ef0f7c080bdbb852bee1`  
		Last Modified: Tue, 07 Feb 2017 22:49:29 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5169ca00673f009eba040239abe8bcb677c4beb282483de9dfb36dfb108af06`  
		Last Modified: Tue, 07 Feb 2017 22:49:28 GMT  
		Size: 1.5 KB (1521 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
