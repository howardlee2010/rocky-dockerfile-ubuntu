FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="barbican-base" build-date="20191030"








RUN usermod --append --home /var/lib/barbican --groups kolla barbican \
    && mkdir -p /var/lib/barbican \
    && chown -R 42403:42403 /var/lib/barbican



    
        
    

RUN apt-get update && apt-get -y install --no-install-recommends uwsgi-plugin-python && apt-get clean && rm -rf /var/lib/apt/lists/*



ADD barbican-base-archive /barbican-base-source
RUN ln -s barbican-base-source/* barbican \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /barbican MySQL-python pastedeploy python-barbicanclient uwsgi \
    && mkdir -p /etc/barbican \
    && cp -r /barbican/etc/barbican/* /etc/barbican/ \
    && chown -R barbican: /etc/barbican



COPY barbican_sudoers /etc/sudoers.d/kolla_barbican_sudoers
COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN chmod 750 /etc/sudoers.d \
    && chmod 640 /etc/sudoers.d/kolla_barbican_sudoers \
    && touch /usr/local/bin/kolla_barbican_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_barbican_extend_start

