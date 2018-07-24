FROM fedora

MAINTAINER Mikhail Chusavitin  <chusavitin@lanit.ru>

ENV NAME="gluster-client" \
    DESC="GlusterFS client on Fedora" \
    VERSION=0 \
    RELEASE=1 \
    ARCH=x86_64 \
    REPO="$FGC" \
    container=docker \
    SRV_ADDRESS="" \
    SRV_SHARE="";

LABEL name="$REPO/$NAME" \
      version="$VERSION" \
      release="$RELEASE.$DISTTAG" \
      architecture="$ARCH" \
      vendor="LANIT, JSC" \
      summary="$DESC" \
      summary="This image has a running glusterfs service ( Fedora + Gluster 3.10 client)" \
      io.k8s.display-name="Gluster 3.10 client based on Fedora" \
      io.k8s.description="Gluster Client Image is based on Fedora Image which is used to mount a glusterfs volume." \
      description="Gluster Client Image is based on Fedora Image which is used to mount a glusterfs volume." \
      io.openshift.tags="gluster,glusterfs,glusterfs-client";

RUN sed -i "s/LANG/\#LANG/g" /etc/locale.conf
RUN dnf --setopt=tsflags=nodocs -y update
RUN dnf --setopt=tsflags=nodocs -y install wget nfs-utils attr iputils iproute \
  && dnf install -y glusterfs-fuse \
  && dnf clean all
RUN mkdir -p /data \
  && mkdir -p /var/log/core;

CMD ["/sbin/mount_glusterfs $SRV_ADDRESS:/$SRV_SHARE /data"]
