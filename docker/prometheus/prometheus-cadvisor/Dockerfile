FROM kolla/ubuntu-source-prometheus-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="prometheus-cadvisor" build-date="20191030"






ENV prometheus_cadvisor_version=0.27.4





RUN curl -ssL -o /opt/cadvisor https://github.com/google/cadvisor/releases/download/v${prometheus_cadvisor_version}/cadvisor && chmod 0755 /opt/cadvisor





