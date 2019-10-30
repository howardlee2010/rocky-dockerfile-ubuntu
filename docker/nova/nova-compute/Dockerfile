FROM kolla/ubuntu-source-nova-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="nova-compute" build-date="20191030"






    

        

        

        # systemd is needed to get python-guestfs installed
        

RUN mkdir -p /etc/ceph

    

RUN apt-get update && apt-get -y install --no-install-recommends ceph-common dosfstools e2fsprogs genisoimage libosinfo-bin multipath-tools nfs-common open-iscsi parted python-guestfs python-libvirt python-rtslib-fb qemu-utils targetcli-fb && apt-get clean && rm -rf /var/lib/apt/lists/*





ADD plugins-archive /
RUN pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt oslo-vmware \
    && if [ "$(ls /plugins)" ]; then \
           pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /plugins/*; \
       fi



COPY extend_start.sh /usr/local/bin/kolla_nova_extend_start
RUN chmod 755 /usr/local/bin/kolla_nova_extend_start \
    && rm -f /etc/machine-id




USER nova