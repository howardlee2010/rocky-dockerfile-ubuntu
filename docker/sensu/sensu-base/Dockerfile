FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="sensu-base" build-date="20191030"








RUN usermod --append --home /var/lib/sensu --groups kolla sensu \
    && mkdir -p /var/lib/sensu \
    && chown -R 42467:42467 /var/lib/sensu



    


RUN apt-get update && apt-get -y install --no-install-recommends sensu && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start

