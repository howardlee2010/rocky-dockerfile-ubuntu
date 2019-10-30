FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="neutron-base" build-date="20191030"








RUN usermod --append --home /var/lib/neutron --groups kolla neutron \
    && mkdir -p /var/lib/neutron \
    && chown -R 42435:42435 /var/lib/neutron





    
RUN apt-get update \
    && apt-get -y install --no-install-recommends haproxy \
    || sed -i '/adduser/,+1 d' /var/lib/dpkg/info/haproxy.postinst \
    && echo "configuring packages" \
    && dpkg --configure -a \
    && echo "done" \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*





    

        

    

RUN apt-get update && apt-get -y install --no-install-recommends conntrack dnsmasq dnsmasq-utils haproxy iproute2 ipset iptables iputils-arping iputils-ping keepalived net-tools openvswitch-switch python-openvswitch radvd uuid-runtime && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD neutron-base-archive /neutron-base-source
ADD plugins-archive /





RUN ln -s neutron-base-source/* neutron \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /neutron oslo-vmware \
    && mkdir -p /etc/neutron /usr/share/neutron \
    && cp -r /neutron/etc/* /etc/neutron/ \
    && cp -r /neutron/etc/neutron/* /etc/neutron/ \
    && cp /neutron/etc/api-paste.ini /usr/share/neutron \
    && mv /etc/neutron/neutron/ /etc/neutron/plugins/ \
    && chown -R neutron: /etc/neutron /usr/share/neutron \
    && sed -i 's|^exec_dirs.*|exec_dirs=/var/lib/kolla/venv/bin,/sbin,/usr/sbin,/bin,/usr/bin,/usr/local/bin,/usr/local/sbin|g' /etc/neutron/rootwrap.conf \
    && if [ "$(ls /plugins)" ]; then \
        pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /plugins/* \
        && for neutron_plugins in $(ls /plugins); do \
            if [ -d "/plugins/$neutron_plugins/etc/neutron/rootwrap.d" ]; then \
                cp /plugins/$neutron_plugins/etc/neutron/rootwrap.d/* /etc/neutron/rootwrap.d; \
            fi; \
        done; \
    fi



COPY neutron_sudoers /etc/sudoers.d/kolla_neutron_sudoers
COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_neutron_sudoers \
    && touch /usr/local/bin/kolla_neutron_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_neutron_extend_start

