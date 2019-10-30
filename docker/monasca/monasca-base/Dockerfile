FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="monasca-base" build-date="20191030"








RUN usermod --append --home /var/lib/monasca --groups kolla monasca \
    && mkdir -p /var/lib/monasca \
    && chown -R 42431:42431 /var/lib/monasca




    

        

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN truncate -s 0 /etc/apache2/ports.conf

    





RUN true \
    && mkdir -p /etc/monasca \
    && chown -R monasca: /etc/monasca




COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN touch /usr/local/bin/kolla_monasca_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_monasca_extend_start

