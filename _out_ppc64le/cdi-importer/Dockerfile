FROM quay.io/centos/centos:stream9

RUN yum update -y && yum install -y --allowerasing acl util-linux-core \
coreutils-single glibc-minimal-langpack libcurl-minimal tar

RUN yum -y install libnbd \
libstdc++ \
nbdkit-server \
nbdkit-basic-filters \
nbdkit-curl-plugin \
nbdkit-xz-filter \
nbdkit-gzip-filter \
qemu-img

COPY ./cdi-importer-v1.54.0-linux-ppc64le /usr/bin/cdi-importer
COPY ./cdi-containerimage-server-v1.54.0-linux-ppc64le /usr/bin/cdi-containerimage-server
COPY ./cdi-image-size-detection-v1.54.0-linux-ppc64le /usr/bin/cdi-image-size-detection
COPY ./cdi-source-update-poller-v1.54.0-linux-ppc64le /usr/bin/cdi-source-update-poller

ENTRYPOINT ["/usr/bin/cdi-importer","-alsologtostderr"]
