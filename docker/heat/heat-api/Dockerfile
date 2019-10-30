FROM kolla/ubuntu-source-heat-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="heat-api" build-date="20191030"







COPY extend_start.sh /usr/local/bin/kolla_heat_extend_start
RUN chmod 755 /usr/local/bin/kolla_heat_extend_start




USER heat