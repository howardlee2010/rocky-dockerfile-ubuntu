FROM kolla/ubuntu-source-monasca-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="monasca-api" build-date="20191030"







    
        
    
RUN apt-get update && apt-get -y install --no-install-recommends mariadb-client && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD monasca-api-archive /monasca-api-source



RUN ln -s monasca-api-source/* monasca-api \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt influxdb /monasca-api



COPY extend_start.sh /usr/local/bin/kolla_monasca_extend_start
RUN chmod 755 /usr/local/bin/kolla_monasca_extend_start



