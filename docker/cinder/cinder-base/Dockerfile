FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="cinder-base" build-date="20191030"








RUN usermod --append --home /var/lib/cinder --groups kolla cinder \
    && mkdir -p /var/lib/cinder \
    && chown -R 42407:42407 /var/lib/cinder



    
        
    
RUN apt-get update && apt-get -y install --no-install-recommends ceph-common lvm2 cryptsetup qemu-utils && apt-get clean && rm -rf /var/lib/apt/lists/*



ADD cinder-base-archive /cinder-base-source
RUN ln -s cinder-base-source/* cinder \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /cinder \
    && mkdir -p /etc/cinder \
    && cp -r /cinder/etc/cinder/* /etc/cinder/ \
    && chown -R cinder: /etc/cinder \
    && sed -i 's|^exec_dirs.*|exec_dirs=/var/lib/kolla/venv/bin,/sbin,/usr/sbin,/bin,/usr/bin,/usr/local/bin,/usr/local/sbin|g' /etc/cinder/rootwrap.conf



COPY cinder_sudoers /etc/sudoers.d/kolla_cinder_sudoers
COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_cinder_sudoers \
    && touch /usr/local/bin/kolla_cinder_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_cinder_extend_start

