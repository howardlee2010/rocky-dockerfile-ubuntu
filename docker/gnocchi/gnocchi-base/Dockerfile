FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="gnocchi-base" build-date="20191030"








RUN usermod --append --home /var/lib/gnocchi --groups kolla gnocchi \
    && mkdir -p /var/lib/gnocchi \
    && chown -R 42416:42416 /var/lib/gnocchi



    

       

        # on x86-64 pip grabs precompiled numpy/scipy - on aarch64/ppc64le
        # it needs to be built

        

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi librados-dev python-ldappool && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN truncate -s 0 /etc/apache2/ports.conf

   
ADD gnocchi-base-archive /gnocchi-base-source



RUN ln -s gnocchi-base-source/* gnocchi \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt gnocchiclient /gnocchi[keystone,mysql,file,ceph,s3] \
    && mkdir -p /etc/gnocchi \
    && chown -R gnocchi: /etc/gnocchi



COPY extend_start.sh /usr/local/bin/kolla_extend_start
COPY gnocchi_sudoers /etc/sudoers.d/kolla_gnocchi_sudoers

RUN chmod 750 /etc/sudoers.d \
    && chmod 640 /etc/sudoers.d/kolla_gnocchi_sudoers \
    && touch /usr/local/bin/kolla_gnocchi_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_gnocchi_extend_start

