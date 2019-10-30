FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="tripleo-ui" build-date="20191030"






    
RUN echo 'tripleo-ui not yet available for ubuntu' && /bin/false
    

ADD tripleo-ui-archive /tripleo-ui-source
RUN cd tripleo-ui-source/package \
    && npm install \
    && npm run build \
    && mkdir -p /var/www/openstack-tripleo-ui \
    && cp -rf dist /var/www/openstack-tripleo-ui/



COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start


