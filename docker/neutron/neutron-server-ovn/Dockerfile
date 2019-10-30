FROM kolla/ubuntu-source-neutron-server:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="neutron-server-ovn" build-date="20191030"

USER root







ADD plugins-archive /



RUN if [ "$(ls /plugins)" ]; then \
        pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /plugins/*; \
    fi






USER neutron