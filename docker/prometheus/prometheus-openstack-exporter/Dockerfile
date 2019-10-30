FROM kolla/ubuntu-source-prometheus-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="prometheus-openstack-exporter" build-date="20191030"




ENV prometheus_openstack_exporter_version=0.0.3



RUN curl -sSL -o /tmp/prometheus_openstack_exporter.tar.gz https://github.com/Linaro/openstack-exporter/releases/download/v${prometheus_openstack_exporter_version}/openstack-exporter-${prometheus_openstack_exporter_version}.linux-${prometheus_arch}.tar.gz \
    && tar xvf /tmp/prometheus_openstack_exporter.tar.gz -C /opt/ \
    && rm -f /tmp/prometheus_openstack_exporter.tar.gz \
    && ln -s /opt/openstack-exporter* /opt/openstack-exporter





USER prometheus