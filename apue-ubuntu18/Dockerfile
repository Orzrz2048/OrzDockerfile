FROM ubuntu:18.04
MAINTAINER renz2048 <renzhengandquiet@gmail.com>
ENV REFRESHED_AT 2018-12-19
RUN apt-get update && apt-get install -y \
    vim \
    libbsd-dev \
    build-essential \
    iproute2 \
    openssh-server
VOLUME ["/data"]
EXPOSE 22