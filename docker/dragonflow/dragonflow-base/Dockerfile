FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="dragonflow-base" build-date="20191030"








RUN usermod --append --home /var/lib/dragonflow --groups kolla dragonflow \
    && mkdir -p /var/lib/dragonflow \
    && chown -R 42464:42464 /var/lib/dragonflow





    



RUN apt-get update && apt-get -y install --no-install-recommends libzmq3-dev && apt-get clean && rm -rf /var/lib/apt/lists/*



ADD dragonflow-base-archive /dragonflow-base-source
RUN ln -s dragonflow-base-source/* dragonflow \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /dragonflow \
    && mkdir -p /etc/dragonflow \
    && cp -r /dragonflow/etc/* /etc/dragonflow/ \
    && chown -R dragonflow: /etc/dragonflow



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_dragonflow_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_dragonflow_extend_start

