FROM quay.io/centos/centos:stream9

RUN yum update -y && yum install -y --allowerasing acl util-linux-core \
coreutils-single glibc-minimal-langpack libcurl-minimal tar

COPY ./cdi-cloner-v1.54.0-linux-ppc64le /usr/bin/cdi-cloner
COPY ./cloner_startup.sh /usr/bin/cloner_startup.sh

ENTRYPOINT /usr/bin/cloner_startup.sh
