FROM kolla/ubuntu-source-kuryr-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="kuryr-libnetwork" build-date="20191030"






    

        

    
RUN apt-get update && apt-get -y install --no-install-recommends bridge-utils openvswitch-switch && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD kuryr-libnetwork-archive /kuryr-libnetwork-source



RUN ln -s kuryr-libnetwork-source/* kuryr-libnetwork \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /kuryr-libnetwork




