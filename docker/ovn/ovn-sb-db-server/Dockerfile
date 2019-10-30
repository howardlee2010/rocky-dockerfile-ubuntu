FROM kolla/ubuntu-source-ovn-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ovn-sb-db-server" build-date="20191030"






    


RUN apt-get update && apt-get -y install --no-install-recommends ovn-central && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY extend_start.sh /usr/local/bin/kolla_ovn_extend_start
COPY start_sb_db_server.sh /usr/local/bin/start-sb-db-server
RUN chmod 755 /usr/local/bin/kolla_ovn_extend_start \
              /usr/local/bin/start-sb-db-server


