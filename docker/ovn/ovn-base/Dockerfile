FROM kolla/ubuntu-source-openvswitch-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ovn-base" build-date="20191030"






    


RUN apt-get update && apt-get -y install --no-install-recommends ovn-common && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_ovn_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_ovn_extend_start

