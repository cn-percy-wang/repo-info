## `elixir:slim`

```console
$ docker pull elixir@sha256:055aa95677587c48d16bb54c2416dd745361fbbccd5e36fa7428d5fe64a0e3e6
```

-	Platforms:
	-	linux; amd64

### `elixir:slim` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **156.8 MB (156788207 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6a4c6ca854738d231c71df038a57cf920ffedaaf1be0789a9f552721ed0f5b8e`
-	Default Command: `["iex"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Mon, 20 Feb 2017 17:42:06 GMT
ENV OTP_VERSION=19.2.3
# Mon, 20 Feb 2017 17:47:59 GMT
RUN set -xe 	&& OTP_DOWNLOAD_URL="https://github.com/erlang/otp/archive/OTP-${OTP_VERSION}.tar.gz" 	&& OTP_DOWNLOAD_SHA256="51dd3eda2b5e835588ed215328c3943b69bc353d892577411570641f37c51ad8" 	&& runtimeDeps=' 		libodbc1 		libssl1.0.0 		libsctp1 		libwxgtk3.0-0 	' 	&& buildDeps=' 		curl 		ca-certificates 		autoconf 		gcc 		make 		libncurses-dev 		unixodbc-dev 		libssl-dev 		libsctp-dev 		libwxgtk3.0-dev 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $runtimeDeps 	&& apt-get install -y --no-install-recommends $buildDeps 	&& curl -fSL -o otp-src.tar.gz "$OTP_DOWNLOAD_URL" 	&& echo "$OTP_DOWNLOAD_SHA256 otp-src.tar.gz" | sha256sum -c - 	&& mkdir -p /usr/src/otp-src 	&& tar -xzf otp-src.tar.gz -C /usr/src/otp-src --strip-components=1 	&& rm otp-src.tar.gz 	&& cd /usr/src/otp-src 	&& ./otp_build autoconf 	&& ./configure 		--enable-sctp 		--enable-dirty-schedulers 	&& make -j$(nproc) 	&& make install 	&& find /usr/local -name examples | xargs rm -rf 	&& apt-get purge -y --auto-remove $buildDeps 	&& rm -rf /usr/src/otp-src /var/lib/apt/lists/*
# Mon, 20 Feb 2017 17:48:01 GMT
CMD ["erl"]
# Mon, 20 Feb 2017 19:21:15 GMT
ENV ELIXIR_VERSION=v1.4.2 LANG=C.UTF-8
# Mon, 20 Feb 2017 19:21:31 GMT
RUN set -xe 	&& ELIXIR_DOWNLOAD_URL="https://github.com/elixir-lang/elixir/releases/download/${ELIXIR_VERSION}/Precompiled.zip" 	&& ELIXIR_DOWNLOAD_SHA256="3ff610166612db10d3f97895972882a6912e99628e31116d22406389c1de48cc"	&& buildDeps=' 		ca-certificates 		curl 		unzip 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& curl -fSL -o elixir-precompiled.zip $ELIXIR_DOWNLOAD_URL 	&& echo "$ELIXIR_DOWNLOAD_SHA256 elixir-precompiled.zip" | sha256sum -c - 	&& unzip -d /usr/local elixir-precompiled.zip 	&& rm elixir-precompiled.zip 	&& apt-get purge -y --auto-remove $buildDeps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 20 Feb 2017 19:21:32 GMT
CMD ["iex"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5c3f2c600295072972218d31a58d657cfae73dfc478fa8ebf7cd4f1a20860dbb`  
		Last Modified: Mon, 20 Feb 2017 17:51:24 GMT  
		Size: 101.4 MB (101356947 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0c702cebe4280fcfefc4ee5c2932e52b8ed2ca4b13282ac35d512acafcae1e4`  
		Last Modified: Mon, 20 Feb 2017 19:23:15 GMT  
		Size: 4.1 MB (4070050 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
