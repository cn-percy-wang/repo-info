## `chronograf:latest`

```console
$ docker pull chronograf@sha256:067d60f74a3c6fd8ccf29783664a4203e683178d8b3f4e015b4526dfb53ce6a7
```

-	Platforms:
	-	linux; amd64

### `chronograf:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **73.9 MB (73904784 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fef1870237bf600c6ba5f46e8f298fb487d915384b8c143f690933fa829c8ef3`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["chronograf"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 00:00:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jan 2017 00:07:41 GMT
RUN gpg     --keyserver hkp://ha.pool.sks-keyservers.net     --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5
# Tue, 17 Jan 2017 00:07:42 GMT
ENV CHRONOGRAF_VERSION=0.13.0
# Tue, 17 Jan 2017 00:07:46 GMT
RUN wget -q https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_amd64.deb.asc &&     wget -q https://dl.influxdata.com/chronograf/releases/chronograf_${CHRONOGRAF_VERSION}_amd64.deb &&     gpg --batch --verify chronograf_${CHRONOGRAF_VERSION}_amd64.deb.asc chronograf_${CHRONOGRAF_VERSION}_amd64.deb &&     dpkg -i chronograf_${CHRONOGRAF_VERSION}_amd64.deb &&     rm -f chronograf_${CHRONOGRAF_VERSION}_amd64.deb*
# Tue, 17 Jan 2017 00:07:47 GMT
COPY file:6bd8f62167b75e75bb429d6dda670ec917256913ff3370f929e2c8d9e14b475e in /etc/chronograf/chronograf.conf 
# Tue, 17 Jan 2017 00:07:47 GMT
EXPOSE 10000/tcp
# Tue, 17 Jan 2017 00:07:47 GMT
ENV PATH=/opt/chronograf:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 17 Jan 2017 00:07:48 GMT
VOLUME [/var/lib/chronograf]
# Tue, 17 Jan 2017 00:07:48 GMT
COPY file:fc95049005144e726efe031fc5e003a8eedf95c50f0041c41c3161e64cf9dbbe in /entrypoint.sh 
# Tue, 17 Jan 2017 00:07:49 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 17 Jan 2017 00:07:49 GMT
CMD ["chronograf"]
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
	-	`sha256:91ad275dba43646f7c2183a84e5c047b670830d0406730648bc481d55a2c7fbc`  
		Last Modified: Wed, 18 Jan 2017 03:16:22 GMT  
		Size: 6.8 KB (6752 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bf048a978a86b9f04809f5812cb9cc2891436cd3f45ed989fdf607795b510b3`  
		Last Modified: Wed, 18 Jan 2017 03:16:24 GMT  
		Size: 4.0 MB (4000991 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f24a80b707d3e2765b16c3ee235790b4dcbe137f614e306735943efe30f64d8`  
		Last Modified: Wed, 18 Jan 2017 03:16:22 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad9516fb77a19683b69b4004398f50592f00d16c9bf4c78f03e1d71ef60a5942`  
		Last Modified: Wed, 18 Jan 2017 03:16:22 GMT  
		Size: 185.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
