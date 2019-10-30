FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ceph-base" build-date="20191030"








RUN usermod --append --home /var/lib/ceph --groups kolla ceph \
    && mkdir -p /var/lib/ceph \
    && chown -R 64045:64045 /var/lib/ceph




   

    
        
    


RUN apt-get update && apt-get -y install --no-install-recommends btrfs-tools ceph ceph-mds e2fsprogs hdparm parted radosgw xfsprogs ceph-fuse && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start

