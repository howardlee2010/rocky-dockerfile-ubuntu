FROM kolla/ubuntu-source-neutron-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="neutron-l3-agent" build-date="20191030"






   
      
   

RUN apt-get update && apt-get -y install --no-install-recommends strongswan radvd dibbler-client && apt-get clean && rm -rf /var/lib/apt/lists/*






USER neutron