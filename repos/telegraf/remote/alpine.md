## `telegraf:alpine`

```console
$ docker pull telegraf@sha256:c1a752ed23367bbf3b230104b4189f42e70914c258754263287fb48fa767a3c1
```

-	Platforms:
	-	linux; amd64

### `telegraf:alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **9.2 MB (9157857 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7ebf97b727040511a7f8f92cdfb09d013181d0fbd99b39e584dd88a70b1418f8`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Tue, 27 Dec 2016 18:17:25 GMT
ADD file:92ab746eb22dd3ed2b87469c719adf3c1bed7302653bbd76baafd7cfd95e911e in / 
# Wed, 01 Feb 2017 19:37:21 GMT
ENV TELEGRAF_VERSION=1.2.1
# Wed, 01 Feb 2017 19:37:22 GMT
RUN apk add --no-cache ca-certificates &&     update-ca-certificates
# Wed, 01 Feb 2017 19:37:30 GMT
RUN apk add --no-cache --virtual .build-deps wget gnupg tar &&     gpg --keyserver hkp://ha.pool.sks-keyservers.net         --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5 &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Wed, 01 Feb 2017 19:37:31 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Wed, 01 Feb 2017 19:37:32 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Wed, 01 Feb 2017 19:37:32 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 01 Feb 2017 19:37:33 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:0a8490d0dfd399b3a50e9aaa81dba0d425c3868762d46526b41be00886bcc28b`  
		Last Modified: Tue, 27 Dec 2016 18:19:22 GMT  
		Size: 1.9 MB (1902063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43b0bf44b316fed43fd60024bf3723b0094d82d21d39877c2a3889121f707c77`  
		Last Modified: Wed, 01 Feb 2017 19:39:43 GMT  
		Size: 352.8 KB (352762 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7932c2dd9f94e7569cf336caa3b2e95418269ec054ace60e71441db8d55da26e`  
		Last Modified: Wed, 01 Feb 2017 19:39:48 GMT  
		Size: 6.9 MB (6902849 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b91da3ffc42f8293eff4848e60b3ebe8dde82837c2a53736a3b3fa8115e61a19`  
		Last Modified: Wed, 01 Feb 2017 19:39:44 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
