FROM kolla/ubuntu-source-openvswitch-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="openvswitch-vswitchd" build-date="20191030"



COPY extend_start.sh /usr/local/bin/kolla_openvswitch_extend_start
RUN chmod 755 /usr/local/bin/kolla_openvswitch_extend_start


