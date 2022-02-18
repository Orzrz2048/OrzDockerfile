FROM ubuntu:18.04
MAINTAINER renz2048 <renzhengandquiet@gmail.com>
ENV REFRESHED_AT 2018-12-19
RUN apt-get update && apt-get install -y \
    make \
    autoconf \
    python \
    libtool-bin \
    libexpat1-dev \
    build-essential \
  && rm -rf /var/lib/apt/lists/*
ADD httpd-2.4.37.tar.gz /root
ADD apr-1.6.5.tar.gz /root
ADD apr-util-1.6.1.tar.gz /root
ADD pcre-8.42.tar.gz /root
RUN mv /root/httpd-2.4.37 /root/httpd && \
  mv /root/apr-1.6.5 /root/httpd/srclib/apr && \
  mv /root/apr-util-1.6.1 /root/httpd/srclib/apr-util && \
  mv /root/pcre-8.42 /root/httpd/srclib/pcre
WORKDIR /root/httpd/srclib/apr
RUN ./buildconf && \
  ./configure --prefix=/usr/local/apr && \
  make && \
  make install
WORKDIR /root/httpd/srclib/apr-util
RUN ./buildconf && \
  ./configure --prefix=/usr/local/apr-util --with-apr=/usr/local/apr && \
  make && \
  make install
WORKDIR /root/httpd/srclib/pcre
RUN ./configure --prefix=/usr/local/pcre && \
  make && \
  make install
WORKDIR /root/httpd
RUN ./buildconf && \
  ./configure --prefix=/usr/local/apache2 \
    --with-apr=/usr/local/apr \
    --with-apr-util=/usr/local/apr-util \
    --with-pcre=/usr/local/pcre && \
  make && \
  make install
EXPOSE 80
