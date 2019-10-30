FROM kolla/ubuntu-source-neutron-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="neutron-lbaas-agent" build-date="20191030"






RUN apt-get update && apt-get -y install --no-install-recommends haproxy && apt-get clean && rm -rf /var/lib/apt/lists/*



ADD neutron-lbaas-agent-archive /neutron-lbaas-agent-source



RUN ln -s neutron-lbaas-agent-source/* neutron_lbaas \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /neutron_lbaas \
    && cp /neutron_lbaas/etc/neutron/rootwrap.d/* /etc/neutron/rootwrap.d \
    && sed -i 's|^exec_dirs.*|exec_dirs=/var/lib/kolla/venv/bin,/sbin,/usr/sbin,/bin,/usr/bin,/usr/local/bin,/usr/local/sbin|g' /etc/neutron/rootwrap.conf



COPY extend_start.sh /usr/local/bin/kolla_neutron_extend_start
RUN chmod 755 /usr/local/bin/kolla_neutron_extend_start




USER neutron