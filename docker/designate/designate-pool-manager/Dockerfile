FROM kolla/ubuntu-source-designate-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="designate-pool-manager" build-date="20191030"





# The bind9 package here is only to provide the rndc binary.

    
       
    

RUN apt-get update && apt-get -y install --no-install-recommends bind9 && apt-get clean && rm -rf /var/lib/apt/lists/*




USER designate