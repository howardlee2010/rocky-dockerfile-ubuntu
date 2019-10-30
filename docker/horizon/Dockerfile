FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="horizon" build-date="20191030"








RUN usermod --append --home /var/lib/horizon --groups kolla horizon \
    && mkdir -p /var/lib/horizon \
    && chown -R 42420:42420 /var/lib/horizon



    

        

RUN apt-get update && apt-get -y install --no-install-recommends apache2 gettext libapache2-mod-wsgi locales tzdata && apt-get clean && rm -rf /var/lib/apt/lists/*


RUN echo > /etc/apache2/ports.conf \
    && ln -s ../mods-available/headers.load  /etc/apache2/mods-enabled/headers.load


    

ADD horizon-archive /horizon-source
ADD plugins-archive /





RUN ln -s horizon-source/* horizon \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /horizon \
    && mkdir -p /etc/openstack-dashboard \
    && cp -r /horizon/openstack_dashboard/conf/* /etc/openstack-dashboard/ \
    && cp /horizon/openstack_dashboard/local/local_settings.py.example /etc/openstack-dashboard/local_settings \
    && cp /horizon/manage.py /var/lib/kolla/venv/bin/manage.py \
    && if [ "$(ls /plugins)" ]; then \
           pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /plugins/*; \
       fi \
    && for locale in  /var/lib/kolla/venv/lib/python2.7/site-packages/*/locale; do \
           (cd ${locale%/*} && /var/lib/kolla/venv/bin/python /var/lib/kolla/venv/bin/manage.py compilemessages) \
       done \
    && chown -R horizon: /etc/openstack-dashboard /var/lib/kolla/venv/lib/python2.7/site-packages/static



COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start


