FROM ubuntu:18.04
MAINTAINER renz2048 <renzhengandquiet@gmail.com>
ENV REFRESHED_AT 2018-12-19
RUN apt-get update && apt-get install -y ca-certificates && \
    echo > /etc/apt/sources.list && \
    echo "deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse" > /etc/apt/sources.list && \
    echo "deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse" >> /etc/apt/sources.list && \
    echo "deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse" >> /etc/apt/sources.list && \
    echo "deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse" >> /etc/apt/sources.list && \
    apt-get update && apt-get install -y \
    vim \
    libbsd-dev \
    build-essential \
    iproute2 \
    openssh-server
VOLUME ["/data"]
EXPOSE 22