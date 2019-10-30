FROM kolla/ubuntu-source-ceilometer-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ceilometer-ipmi" build-date="20191030"






    
        
    



RUN apt-get update && apt-get -y install --no-install-recommends ipmitool && apt-get clean && rm -rf /var/lib/apt/lists/*




USER ceilometer