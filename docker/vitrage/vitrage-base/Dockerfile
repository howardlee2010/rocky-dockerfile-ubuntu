FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="vitrage-base" build-date="20191030"








RUN usermod --append --home /var/lib/vitrage --groups kolla vitrage \
    && mkdir -p /var/lib/vitrage \
    && chown -R 42459:42459 /var/lib/vitrage




    

        

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi python-ldappool && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN echo > /etc/apache2/ports.conf




ADD vitrage-base-archive /vitrage-base-source
RUN ln -s vitrage-base-source/* vitrage \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /vitrage \
    && mkdir -p /etc/vitrage /var/www/cgi-bin/vitrage \
    && cp -r /vitrage/etc/vitrage/* /etc/vitrage/ \
    && cp /vitrage/vitrage/api/app.wsgi /var/www/cgi-bin/vitrage \
    && chown -R vitrage: /etc/vitrage /var/www/cgi-bin/vitrage



COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN touch /usr/local/bin/kolla_vitrage_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_vitrage_extend_start

