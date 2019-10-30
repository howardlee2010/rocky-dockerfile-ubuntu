FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="keystone-base" build-date="20191030"








RUN usermod --append --home /var/lib/keystone --groups kolla keystone \
    && mkdir -p /var/lib/keystone \
    && chown -R 42425:42425 /var/lib/keystone



    
        
RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-auth-mellon libapache2-mod-auth-openidc libapache2-mod-wsgi python-ldappool && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN echo > /etc/apache2/ports.conf

    


ADD keystone-base-archive /keystone-base-source



RUN ln -s keystone-base-source/* keystone \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /keystone \
    && mkdir -p /etc/keystone /var/www/cgi-bin/keystone \
    && cp -r /keystone/etc/* /etc/keystone/ \
    && cp /var/lib/kolla/venv/bin/keystone-wsgi-admin /var/www/cgi-bin/keystone/admin \
    && cp /var/lib/kolla/venv/bin/keystone-wsgi-public /var/www/cgi-bin/keystone/main \
    && chown -R keystone: /etc/keystone /var/www/cgi-bin/keystone




RUN chown -R keystone: /var/www/cgi-bin/keystone \
    && chmod 755 /var/www/cgi-bin/keystone/*

