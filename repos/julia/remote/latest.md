## `julia:latest`

```console
$ docker pull julia@sha256:0a083df8da7640eadcbdc44acd7c549c7e66db5868e72db201477cf9f0ff2afd
```

-	Platforms:
	-	linux; amd64

### `julia:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **123.2 MB (123181202 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:183ba11b1cb8d7091523cf45d73725ea4daae15a98118486962cd8cda060077c`
-	Default Command: `["julia"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 17:13:36 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends ca-certificates 	&& rm -rf /var/lib/apt/lists/*
# Tue, 17 Jan 2017 17:13:37 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 17 Jan 2017 17:13:37 GMT
ENV JULIA_VERSION=0.5.0
# Tue, 17 Jan 2017 17:13:54 GMT
RUN mkdir $JULIA_PATH 	&& apt-get update && apt-get install -y curl 	&& curl -sSL "https://julialang.s3.amazonaws.com/bin/linux/x64/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-x86_64.tar.gz" -o julia.tar.gz 	&& curl -sSL "https://julialang.s3.amazonaws.com/bin/linux/x64/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-x86_64.tar.gz.asc" -o julia.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 3673DF529D9049477F76B37566E3C7DC03D6E495 	&& gpg --batch --verify julia.tar.gz.asc julia.tar.gz 	&& rm -r "$GNUPGHOME" julia.tar.gz.asc 	&& tar -xzf julia.tar.gz -C $JULIA_PATH --strip-components 1 	&& rm -rf /var/lib/apt/lists/* julia.tar.gz*
# Tue, 17 Jan 2017 17:13:54 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 17 Jan 2017 17:13:55 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eefa026362fb22d53700eef28bbba3878614cfab8c0058fd772661f21a50b2a1`  
		Last Modified: Wed, 18 Jan 2017 04:20:05 GMT  
		Size: 2.8 MB (2815157 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9a9f4e4cb1173a02ffc6f0cf90b1cab6105c74023c6896d0941db2acdab572c9`  
		Last Modified: Wed, 18 Jan 2017 04:20:27 GMT  
		Size: 69.0 MB (69004835 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
