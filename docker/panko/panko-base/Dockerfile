FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="panko-base" build-date="20191030"








RUN usermod --append --home /var/lib/panko --groups kolla panko \
    && mkdir -p /var/lib/panko \
    && chown -R 42438:42438 /var/lib/panko



    

       

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi python-ldappool && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN truncate -s 0 /etc/apache2/ports.conf

   
ADD panko-base-archive /panko-base-source



RUN ln -s panko-base-source/* panko \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /panko pymongo \
    && mkdir -p /etc/panko \
    && cp -r /panko/etc/panko/* /etc/panko/ \
    && chown -R panko: /etc/panko



COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_panko_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_panko_extend_start

