FROM        ghcr.io/graalvm/jdk:ol8-java11

LABEL       author="Softwarenoob" maintainer="admin@softwarenoob.com"

RUN         microdnf update \
            && microdnf install -y curl ca-certificates openssl git tar sqlite fontconfig tzdata iproute \
            && microdnf clean all \
            && adduser --home-dir /home/container container

ENV         LC_ALL=en_US.UTF-8
ENV         LANG=en_US.UTF-8
ENV         LANGUAGE=en_US.UTF-8

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
