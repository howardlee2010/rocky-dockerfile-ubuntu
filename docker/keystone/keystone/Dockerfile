FROM kolla/ubuntu-source-keystone-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="keystone" build-date="20191030"





COPY keystone_bootstrap.sh /usr/local/bin/kolla_keystone_bootstrap
COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_keystone_bootstrap


    
        
    
RUN apt-get update && apt-get -y install --no-install-recommends libapache2-mod-auth-gssapi && apt-get clean && rm -rf /var/lib/apt/lists/*
ADD plugins-archive /



RUN if [ "$(ls /plugins)" ]; then \
        pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /plugins/* requests-kerberos; \
    fi




