FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="grafana" build-date="20191030"









RUN usermod --append --home /usr/share/grafana --groups kolla grafana \
    && mkdir -p /usr/share/grafana \
    && chown -R 42417:42417 /usr/share/grafana



RUN apt-get update && apt-get -y install --no-install-recommends grafana && apt-get clean && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/share/grafana

COPY grafana_sudoers /etc/sudoers.d/kolla_grafana_sudoers
COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN grafana-cli plugins install gnocchixyz-gnocchi-datasource \
    && grafana-cli plugins install grafana-influxdb-08-datasource \
    && chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_grafana_sudoers \
    && chmod 755 /usr/local/bin/kolla_extend_start




USER grafana