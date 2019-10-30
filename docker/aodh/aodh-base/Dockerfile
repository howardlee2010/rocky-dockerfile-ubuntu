FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="aodh-base" build-date="20191030"








RUN usermod --append --home /var/lib/aodh --groups kolla aodh \
    && mkdir -p /var/lib/aodh \
    && chown -R 42402:42402 /var/lib/aodh



    

       

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi python-ldappool && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN mkdir -p /var/www/cgi-bin/aodh \
    && echo > /etc/apache2/ports.conf
    

ADD aodh-base-archive /aodh-base-source



RUN ln -s aodh-base-source/* aodh \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /aodh pymongo \
    && mkdir -p /etc/aodh /var/www/cgi-bin/aodh \
    && cp /aodh/aodh/api/app.wsgi /var/www/cgi-bin/aodh \
    && chown -R aodh: /etc/aodh /var/www/cgi-bin/aodh



COPY extend_start.sh /usr/local/bin/kolla_extend_start
COPY aodh_sudoers /etc/sudoers.d/kolla_aodh_sudoers

RUN chmod 750 /etc/sudoers.d \
    && chmod 640 /etc/sudoers.d/kolla_aodh_sudoers \
    && chmod 755 /var/www/cgi-bin/aodh \
    && touch /usr/local/bin/kolla_aodh_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_aodh_extend_start

