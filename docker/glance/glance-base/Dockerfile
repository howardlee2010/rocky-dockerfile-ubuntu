FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="glance-base" build-date="20191030"








RUN usermod --append --home /var/lib/glance --groups kolla glance \
    && mkdir -p /var/lib/glance \
    && chown -R 42415:42415 /var/lib/glance



    

RUN apt-get update && apt-get -y install --no-install-recommends python-rados python-rbd && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD glance-base-archive /glance-base-source



RUN ln -s glance-base-source/* glance \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /glance glance_store[cinder,vmware,swift] \
    && mkdir -p /etc/glance \
    && cp -r /glance/etc/* /etc/glance/ \
    && chown -R glance: /etc/glance



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_glance_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_glance_extend_start

