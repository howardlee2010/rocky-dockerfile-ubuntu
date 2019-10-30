FROM kolla/ubuntu-source-neutron-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="neutron-server" build-date="20191030"







    

    

ADD plugins-archive /
RUN pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt "networking-hyperv>=5.0.0,<6.0.0" \
    && if [ "$(ls /plugins)" ]; then \
           pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /plugins/*; \
       fi



COPY extend_start.sh /usr/local/bin/kolla_neutron_extend_start
RUN chmod 755 /usr/local/bin/kolla_neutron_extend_start




USER neutron