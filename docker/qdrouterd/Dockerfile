FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="qdrouterd" build-date="20191030"








RUN usermod --append --home /var/lib/qdrouterd --groups kolla qdrouterd \
    && mkdir -p /var/lib/qdrouterd \
    && chown -R 42465:42465 /var/lib/qdrouterd




    

RUN apt-get update && apt-get -y install --no-install-recommends sasl2-bin libpython2.7 qdrouterd qdmanage qdstat && apt-get clean && rm -rf /var/lib/apt/lists/*




COPY extend_start.sh /usr/local/bin/kolla_extend_start
COPY qdrouterd_sudoers /etc/sudoers.d/kolla_qdrouterd_sudoers
RUN chmod 755 /usr/local/bin/kolla_extend_start \
    && chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_qdrouterd_sudoers




USER qdrouterd