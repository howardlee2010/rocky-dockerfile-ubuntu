FROM kolla/ubuntu-source-freezer-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="freezer-api" build-date="20191030"







    
        

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN echo > /etc/apache2/ports.conf
    

ADD freezer-api-archive /freezer-api-source



RUN ln -s freezer-api-source/* freezer-api \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /freezer-api \
    && cp -r /freezer-api/etc/freezer/* /etc/freezer/



COPY extend_start.sh /usr/local/bin/kolla_freezer_extend_start
RUN chmod 755 /usr/local/bin/kolla_freezer_extend_start


