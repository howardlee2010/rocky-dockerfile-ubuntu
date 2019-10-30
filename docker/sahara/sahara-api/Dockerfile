FROM kolla/ubuntu-source-sahara-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="sahara-api" build-date="20191030"







COPY extend_start.sh /usr/local/bin/kolla_sahara_extend_start
RUN chmod 755 /usr/local/bin/kolla_sahara_extend_start




USER sahara