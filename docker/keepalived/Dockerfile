FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="keepalived" build-date="20191030"






    

RUN apt-get update && apt-get -y install --no-install-recommends keepalived && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY check_alive.sh /

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start /check_alive.sh


