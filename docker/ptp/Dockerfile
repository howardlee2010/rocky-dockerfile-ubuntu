FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ptp" build-date="20191030"







RUN apt-get update && apt-get -y install --no-install-recommends linuxptp && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start


