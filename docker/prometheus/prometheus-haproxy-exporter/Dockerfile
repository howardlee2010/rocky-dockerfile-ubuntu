FROM kolla/ubuntu-source-prometheus-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="prometheus-haproxy-exporter" build-date="20191030"




ENV haproxy_exporter_version=0.7.1



RUN curl -sSL -o /tmp/haproxy_exporter.tar.gz https://github.com/prometheus/haproxy_exporter/releases/download/v${haproxy_exporter_version}/haproxy_exporter-${haproxy_exporter_version}.linux-${prometheus_arch}.tar.gz \
    && tar xvf /tmp/haproxy_exporter.tar.gz -C /opt/ \
    && rm -f /tmp/haproxy_exporter.tar.gz \
    && ln -s /opt/haproxy_exporter* /opt/haproxy_exporter





USER prometheus