FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="vmtp" build-date="20191030"








RUN usermod --append --home /var/lib/vmtp --groups kolla vmtp \
    && mkdir -p /var/lib/vmtp \
    && chown -R 42450:42450 /var/lib/vmtp






ADD vmtp-archive /vmtp-source
RUN ln -s vmtp-source/* vmtp \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /vmtp \
    && mkdir -p /etc/vmtp \
    && chown -R vmtp: /etc/vmtp



COPY vmtp_sudoers /etc/sudoers.d/kolla_vmtp_sudoers
RUN chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_vmtp_sudoers




USER vmtp