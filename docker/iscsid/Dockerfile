FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="iscsid" build-date="20191030"






    



RUN apt-get update && apt-get -y install --no-install-recommends open-iscsi python-rtslib-fb targetcli-fb && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN chmod 755 /usr/local/bin/kolla_extend_start \
    && rm /etc/iscsi/initiatorname.iscsi


