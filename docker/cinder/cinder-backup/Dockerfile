FROM kolla/ubuntu-source-cinder-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="cinder-backup" build-date="20191030"






    
        
    



RUN apt-get update && apt-get -y install --no-install-recommends nfs-common && apt-get clean && rm -rf /var/lib/apt/lists/*




USER cinder