FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="novajoin-base" build-date="20191030"








RUN usermod --append --home /var/lib/novajoin --groups kolla novajoin \
    && mkdir -p /var/lib/novajoin \
    && chown -R 42470:42470 /var/lib/novajoin



    
        
    

RUN apt-get update && apt-get -y install --no-install-recommends freeipa-admintools && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD novajoin-base-archive /novajoin-base-source



RUN ln -s novajoin-base-source/* novajoin \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /novajoin \
    && mkdir -p /etc/nova /etc/novajoin \
    && chown -R novajoin: /etc/nova /etc/novajoin



COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 750 /etc/sudoers.d \
    && touch /usr/local/bin/kolla_novajoin_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_novajoin_extend_start

