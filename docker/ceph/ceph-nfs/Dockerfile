FROM kolla/ubuntu-source-ceph-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ceph-nfs" build-date="20191030"






        



RUN apt-get update && apt-get -y install --no-install-recommends nfs-ganesha nfs-ganesha-ceph && apt-get clean && rm -rf /var/lib/apt/lists/*


