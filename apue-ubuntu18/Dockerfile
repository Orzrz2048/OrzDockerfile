FROM ubuntu:18.04
MAINTAINER renz2048 <renzhengandquiet@gmail.com>
ENV REFRESHED_AT 2018-12-19
ADD sources.list /root
RUN mv /root/sources.list /etc/apt/sources.list
RUN apt-get update && apt-get install -y \
    vim \
    wget \
    git \
    libbsd-dev \
    build-essential \
    iproute2 \
    openssh-server \
  && service ssh start
VOLUME ["/data"]
EXPOSE 22