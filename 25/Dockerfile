FROM container-registry.oracle.com/graalvm/jdk:25 

USER root

RUN microdnf update -y && \
    microdnf install -y curl lsof ca-certificates openssl fontconfig tar tzdata iproute libstdc++ && \
    microdnf clean all

RUN useradd -d /home/container -m container

USER container
ENV  USER=container HOME=/home/container
WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD ["/bin/bash", "/entrypoint.sh"]
