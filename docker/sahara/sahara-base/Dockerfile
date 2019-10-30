FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="sahara-base" build-date="20191030"








RUN usermod --append --home /var/lib/sahara --groups kolla sahara \
    && mkdir -p /var/lib/sahara \
    && chown -R 42441:42441 /var/lib/sahara





    

RUN apt-get update && apt-get -y install --no-install-recommends openssh-client && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD sahara-base-archive /sahara-base-source



RUN ln -s sahara-base-source/* sahara \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /sahara \
    && mkdir -p /etc/sahara \
    && cp -r /sahara/etc/sahara/* /etc/sahara/ \
    && chown -R sahara: /etc/sahara \
    && sed -i 's|^exec_dirs.*|exec_dirs=/var/lib/kolla/venv/bin,/sbin,/usr/sbin,/bin,/usr/bin,/usr/local/bin,/usr/local/sbin|g' /etc/sahara/rootwrap.conf



COPY sahara_sudoers /etc/sudoers.d/kolla_sahara_sudoers
COPY extend_start.sh /usr/local/bin/kolla_extend_start

RUN chmod 750 /etc/sudoers.d \
    && chmod 640 /etc/sudoers.d/kolla_sahara_sudoers \
    && touch /usr/local/bin/kolla_sahara_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_sahara_extend_start

