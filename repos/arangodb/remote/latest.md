## `arangodb:latest`

```console
$ docker pull arangodb@sha256:a0e42799a047d91ca55fce727611a909a2bd04560cb46ab2e1d06e0a818967fa
```

-	Platforms:
	-	linux; amd64

### `arangodb:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **127.3 MB (127296124 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5aacf198141660cdf398d51e668dc4a18e1d70a346c94094abdda1d72f919a03`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["arangod"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Mon, 16 Jan 2017 23:59:48 GMT
MAINTAINER Frank Celler <info@arangodb.com>
# Tue, 17 Jan 2017 00:01:38 GMT
ENV ARCHITECTURE=amd64
# Tue, 17 Jan 2017 00:01:39 GMT
ENV DEB_PACKAGE_VERSION=1
# Mon, 20 Feb 2017 17:08:18 GMT
ENV ARANGO_VERSION=3.1.11
# Mon, 20 Feb 2017 17:08:19 GMT
ENV ARANGO_URL=https://www.arangodb.com/repositories/arangodb31/Debian_8.0
# Mon, 20 Feb 2017 17:08:19 GMT
ENV ARANGO_PACKAGE=arangodb3-3.1.11-1_amd64.deb
# Mon, 20 Feb 2017 17:08:20 GMT
ENV ARANGO_PACKAGE_URL=https://www.arangodb.com/repositories/arangodb31/Debian_8.0/amd64/arangodb3-3.1.11-1_amd64.deb
# Mon, 20 Feb 2017 17:08:34 GMT
ENV ARANGO_SIGNATURE_URL=https://www.arangodb.com/repositories/arangodb31/Debian_8.0/amd64/arangodb3-3.1.11-1_amd64.deb.asc
# Mon, 20 Feb 2017 17:08:36 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys CD8CB0F1E0AD5B52E93F41E7EA93F5E56E751E9B
# Mon, 20 Feb 2017 17:08:49 GMT
RUN apt-get update &&     apt-get install -y --no-install-recommends         libjemalloc1 	libsnappy1         ca-certificates         pwgen         curl     &&     rm -rf /var/lib/apt/lists/*
# Mon, 20 Feb 2017 17:08:50 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 20 Feb 2017 17:09:19 GMT
RUN curl -O ${ARANGO_SIGNATURE_URL} &&           curl -O ${ARANGO_PACKAGE_URL} &&             gpg --verify ${ARANGO_PACKAGE}.asc &&     (echo arangodb3 arangodb3/password password test | debconf-set-selections) &&     (echo arangodb3 arangodb3/password_again password test | debconf-set-selections) &&     DEBIAN_FRONTEND="noninteractive" dpkg -i ${ARANGO_PACKAGE} &&     rm -rf /var/lib/arangodb3/* &&     sed -ri         -e 's!127\.0\.0\.1!0.0.0.0!g'         -e 's!^(file\s*=).*!\1 -!'         -e 's!^#\s*uid\s*=.*!uid = arangodb!'         -e 's!^#\s*gid\s*=.*!gid = arangodb!'         /etc/arangodb3/arangod.conf     &&     DEBIAN_FRONTEND="noninteractive" apt-get purge -y --auto-remove ca-certificates &&     rm -f ${ARANGO_PACKAGE}*
# Mon, 20 Feb 2017 17:09:20 GMT
VOLUME [/var/lib/arangodb3 /var/lib/arangodb3-apps]
# Mon, 20 Feb 2017 17:09:21 GMT
COPY file:9f20ed9a2181af8ddc12371a0082e7645aa20b1008b5f484851bcc399e64801e in /entrypoint.sh 
# Mon, 20 Feb 2017 17:09:22 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Mon, 20 Feb 2017 17:09:23 GMT
EXPOSE 8529/tcp
# Mon, 20 Feb 2017 17:09:24 GMT
CMD ["arangod"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6926f0d37430e6fd673444229481ee3f3b55e8c5743f3c6c88e5e7353dcdc234`  
		Last Modified: Mon, 20 Feb 2017 17:11:18 GMT  
		Size: 7.4 KB (7368 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:77c1ae1cb7e5f5b3bebe2916dc3976b25c08a7dd48a25cbe07375dad22647878`  
		Last Modified: Mon, 20 Feb 2017 17:11:20 GMT  
		Size: 6.7 MB (6691300 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:021d63dd47af0862ad9456027792854fcc0d51e93367754f789e3208dab44380`  
		Last Modified: Mon, 20 Feb 2017 17:11:19 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:189ac20d173f52d832731529952eb2234e3a40eb03ea0836f6b1b0f4542c8cff`  
		Last Modified: Mon, 20 Feb 2017 17:11:36 GMT  
		Size: 69.2 MB (69234696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34c4f08e9a8905daa61b9a0e0a78bdbeb29abe4b380f7eccbb24476562a8f5b2`  
		Last Modified: Mon, 20 Feb 2017 17:11:18 GMT  
		Size: 1.4 KB (1436 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
