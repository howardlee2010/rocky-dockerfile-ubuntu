FROM kolla/ubuntu-source-ceph-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ceph-mon" build-date="20191030"



COPY fetch_ceph_keys.py /usr/bin/

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start /usr/bin/fetch_ceph_keys.py


