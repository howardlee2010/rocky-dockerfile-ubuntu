FROM kolla/ubuntu-source-monasca-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="monasca-agent" build-date="20191030"







ADD monasca-agent-archive /monasca-agent-source



RUN ln -s monasca-agent-source/* monasca-agent \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /monasca-agent prometheus_client







USER monasca
