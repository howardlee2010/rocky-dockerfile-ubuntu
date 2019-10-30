FROM kolla/ubuntu-source-ironic-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ironic-conductor" build-date="20191030"






    
        
    



RUN pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt -r /ironic/driver-requirements.txt ironic-staging-drivers


RUN apt-get update && apt-get -y install --no-install-recommends bsdmainutils dosfstools e2fsprogs gdisk ipmitool parted psmisc qemu-utils shellinabox udev xfsprogs && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY extend_start.sh /usr/local/bin/kolla_ironic_extend_start
COPY iscsi_tcp_sudoers /etc/sudoers.d/kolla_iscsi_tcp_sudoers
RUN chmod 755 /usr/local/bin/kolla_ironic_extend_start \
    && chmod 440 /etc/sudoers.d/kolla_iscsi_tcp_sudoers




USER ironic