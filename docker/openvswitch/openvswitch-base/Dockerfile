FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="openvswitch-base" build-date="20191030"








    


RUN apt-get update && apt-get -y install --no-install-recommends openvswitch-switch python-openvswitch python-netifaces tcpdump && apt-get clean && rm -rf /var/lib/apt/lists/*



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN mv /usr/sbin/tcpdump /usr/bin/tcpdump \
    && touch /usr/local/bin/kolla_openvswitch_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_openvswitch_extend_start

