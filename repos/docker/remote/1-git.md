## `docker:1-git`

```console
$ docker pull docker@sha256:f840f4968765dc80dc346c0444770dfdef1aea51e6a216814b830d7766e61921
```

-	Platforms:
	-	linux; amd64

### `docker:1-git` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **42.2 MB (42173062 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:733982e68bdac6c03cbe6149206cdcf052cad89dae93341c76672db701052d4d`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 04 Jan 2017 21:04:10 GMT
RUN apk add --no-cache 		ca-certificates 		curl 		openssl
# Wed, 04 Jan 2017 21:04:27 GMT
ENV DOCKER_BUCKET=get.docker.com
# Thu, 09 Feb 2017 23:44:32 GMT
ENV DOCKER_VERSION=1.13.1
# Thu, 09 Feb 2017 23:44:32 GMT
ENV DOCKER_SHA256=97892375e756fd29a304bd8cd9ffb256c2e7c8fd759e12a55a6336e15100ad75
# Thu, 09 Feb 2017 23:44:38 GMT
RUN set -x 	&& curl -fSL "https://${DOCKER_BUCKET}/builds/Linux/x86_64/docker-${DOCKER_VERSION}.tgz" -o docker.tgz 	&& echo "${DOCKER_SHA256} *docker.tgz" | sha256sum -c - 	&& tar -xzvf docker.tgz 	&& mv docker/* /usr/local/bin/ 	&& rmdir docker 	&& rm docker.tgz 	&& docker -v
# Thu, 09 Feb 2017 23:44:38 GMT
COPY file:a8b1446f032ff01ac092c29a0af328f0b9d47bbee72d1049499f2a9a89ee988a in /usr/local/bin/ 
# Thu, 09 Feb 2017 23:44:39 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 09 Feb 2017 23:44:39 GMT
CMD ["sh"]
# Thu, 09 Feb 2017 23:44:50 GMT
RUN apk add --no-cache 		git 		openssh-client
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8af50e60f15f49e6f8bd6fd84a5388b6de295a9e87ba9bc86878d04b5037d9b7`  
		Last Modified: Wed, 04 Jan 2017 23:28:13 GMT  
		Size: 2.2 MB (2166920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9e5b4bc00ad7eb4efa31cc3518c28d294154919fdfdd1e6d0fedce17627645d4`  
		Last Modified: Fri, 10 Feb 2017 00:04:57 GMT  
		Size: 27.7 MB (27731083 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2ff5ca00fa8dc5245c0dd8456947756714642344c02b07e0d5fbffa70dcfbdae`  
		Last Modified: Fri, 10 Feb 2017 00:04:47 GMT  
		Size: 487.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b9cfc6e1db19f02f2eee266650b24d188f12af34ff2d4dce11f105d26de70d2`  
		Last Modified: Fri, 10 Feb 2017 00:07:35 GMT  
		Size: 10.4 MB (10372509 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
