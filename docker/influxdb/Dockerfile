FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="influxdb" build-date="20191030"








RUN usermod --append --home /var/lib/influxdb --groups kolla influxdb \
    && mkdir -p /var/lib/influxdb \
    && chown -R 42421:42421 /var/lib/influxdb



RUN apt-get update && apt-get -y install --no-install-recommends influxdb && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY influxdb_sudoers /etc/sudoers.d/kolla_influxdb_sudoers
COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_influxdb_sudoers \
    && chmod 755 /usr/local/bin/kolla_extend_start




USER influxdb