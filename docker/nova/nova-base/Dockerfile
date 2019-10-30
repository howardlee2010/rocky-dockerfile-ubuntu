FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="nova-base" build-date="20191030"








RUN usermod --append --home /var/lib/nova --groups kolla nova \
    && usermod --append --groups qemu nova \
    && mkdir -p /var/lib/nova \
    && chown -R 42436:42436 /var/lib/nova



    

        
        
            
        

    

RUN apt-get update && apt-get -y install --no-install-recommends bridge-utils dnsmasq ebtables iproute2 iptables openssh-client openvswitch-switch python-libvirt ovmf && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD nova-base-archive /nova-base-source
ADD plugins-archive /





RUN ln -s nova-base-source/* nova \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /nova \
    && mkdir -p /etc/nova/ \
    && cp -r /nova/etc/nova/* /etc/nova/ \
    && chown -R nova: /etc/nova/ \
    && sed -i 's|^exec_dirs.*|exec_dirs=/var/lib/kolla/venv/bin,/sbin,/usr/sbin,/bin,/usr/bin,/usr/local/bin,/usr/local/sbin|g' /etc/nova/rootwrap.conf \
    && if [ "$(ls /plugins)" ]; then \
        pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /plugins/*; \
    fi

COPY nova_sudoers /etc/sudoers.d/kolla_nova_sudoers
RUN chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_nova_sudoers






COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_nova_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_nova_extend_start

