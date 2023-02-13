FROM quay.io/centos/centos:stream9

RUN yum update -y && yum install -y --allowerasing acl util-linux-core \
coreutils-single glibc-minimal-langpack libcurl-minimal tar

COPY ./cdi-apiserver-v1.54.0-linux-ppc64le /usr/bin/cdi-apiserver

RUN groupadd -g 1001 nonroot-user && useradd -u 1001 -g 1001 -Ms /bin/sh nonroot-user

USER 1001

WORKDIR /home/cdi-apiserver

ENTRYPOINT ["/usr/bin/cdi-apiserver","-alsologtostderr"]
