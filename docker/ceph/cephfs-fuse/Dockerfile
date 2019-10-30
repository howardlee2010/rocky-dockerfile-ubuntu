FROM kolla/ubuntu-source-ceph-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="cephfs-fuse" build-date="20191030"






# Clear any customisation by Kolla to entrypoint & command
ENTRYPOINT ["/usr/bin/ceph-fuse"]
CMD []