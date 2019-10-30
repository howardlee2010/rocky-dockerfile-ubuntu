FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="dind" build-date="20191030"






    

    
        
    

    
RUN apt-get update && apt-get -y install --no-install-recommends btrfs-tools openssh-server docker.io && apt-get clean && rm -rf /var/lib/apt/lists/*



RUN pip --no-cache-dir install --upgrade docker



COPY start.sh /usr/local/bin/kolla_start
RUN chmod 755 /usr/local/bin/kolla_start


