FROM kolla/ubuntu-source-ovsdpdk:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ovsdpdk-db" build-date="20191030"



COPY extend_start.sh /usr/local/bin/kolla_ovsdpdk_extend_start
COPY start_ovsdb_server.sh /usr/local/bin/start-ovsdb-server
RUN chmod 755 /usr/local/bin/kolla_ovsdpdk_extend_start && \
    chmod 755 /usr/local/bin/start-ovsdb-server


