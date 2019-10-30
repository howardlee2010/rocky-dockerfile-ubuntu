# TODO(egonzalez): SFC image is deprecated and will be removed during Queens release
FROM kolla/ubuntu-source-neutron-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="neutron-sfc-agent" build-date="20191030"





COPY extend_start.sh /usr/local/bin/kolla_neutron_extend_start
RUN chmod 755 /usr/local/bin/kolla_neutron_extend_start




USER neutron