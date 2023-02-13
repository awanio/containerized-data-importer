FROM quay.io/centos/centos:stream9

RUN yum update -y && yum install -y --allowerasing acl util-linux-core \
coreutils-single glibc-minimal-langpack libcurl-minimal tar

RUN yum -y install libnbd qemu-img

COPY ./cdi-uploadserver-v1.54.0-linux-ppc64le /usr/bin/cdi-uploadserver

ENTRYPOINT ["/usr/bin/cdi-uploadserver","-alsologtostderr"]
