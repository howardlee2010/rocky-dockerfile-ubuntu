FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="zun-base" build-date="20191030"








RUN usermod --append --home /var/lib/zun --groups kolla zun \
    && mkdir -p /var/lib/zun \
    && chown -R 42463:42463 /var/lib/zun




    

        

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi python-ldappool && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN mkdir -p /var/www/cgi-bin/zun \
    && echo > /etc/apache2/ports.conf
    

ADD zun-base-archive /zun-base-source



RUN ln -s zun-base-source/* zun \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /zun \
    && mkdir -p /etc/zun /var/www/cgi-bin/zun \
    && cp -r /zun/etc/zun/* /etc/zun/ \
    && cp /zun/zun/api/app.wsgi /var/www/cgi-bin/zun \
    && chown -R zun: /etc/zun /var/www/cgi-bin/zun



COPY zun_sudoers /etc/sudoers.d/kolla_zun_sudoers
COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN chmod 750 /etc/sudoers.d \
    && chmod 640 /etc/sudoers.d/kolla_zun_sudoers \
    && touch /usr/local/bin/kolla_zun_extend_start \
    && chmod 755 /var/www/cgi-bin/zun \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_zun_extend_start

