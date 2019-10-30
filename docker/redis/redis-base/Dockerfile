FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="redis-base" build-date="20191030"







RUN usermod --append --home /run/redis --groups kolla redis \
    && mkdir -p /run/redis \
    && chown -R 42460:42460 /run/redis


COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start

