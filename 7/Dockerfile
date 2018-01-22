FROM gcc:7
LABEL maintainer "Ikebe, Ryohji <Ryohji.Ikebe@gmail.com>"

RUN apt-get update\
 && apt-get install --no-install-recommends zip unzip\
 && apt-get upgrade -y\
 && apt-get clean\
 && rm -rf /var/lib/apt/lists/*

ADD protobuf-3.5.1.1.tar.gz /tmp
RUN cd /tmp/protobuf-3.5.1.1\
 && ./autogen.sh\
 && ./configure --prefix=/usr --disable-shared --with-pic\
 && make install\
 && ldconfig\
 && rm -r /tmp/protobuf-3.5.1.1

RUN apt-get remove -y zip unzip\
 && apt-get clean\
 && rm -rf /var/lib/apt/lists/*
