FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="zaqar" build-date="20191030"








RUN usermod --append --home /var/lib/zaqar --groups kolla zaqar \
    && mkdir -p /var/lib/zaqar \
    && chown -R 42452:42452 /var/lib/zaqar





    

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN echo > /etc/apache2/ports.conf


ADD zaqar-archive /zaqar-source



RUN ln -s zaqar-source/* zaqar \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt pymongo /zaqar \
    && mkdir -p /etc/zaqar \
    && cp -r /zaqar/etc/* /etc/zaqar/ \
    && chown -R zaqar: /etc/zaqar



COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start




USER zaqar