FROM debian:bookworm AS build

WORKDIR /src

RUN set -xe; \
    apt-get -yqq update; \
    apt-get -yqq install openssh-server strace net-tools \
    ;

RUN echo "root:unikraft" | chpasswd

RUN mkdir /run/sshd

COPY ./wrapper.sh /usr/bin/wrapper.sh
