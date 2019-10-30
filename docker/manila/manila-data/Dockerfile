FROM kolla/ubuntu-source-manila-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="manila-data" build-date="20191030"






    

        

    



RUN apt-get update && apt-get -y install --no-install-recommends nfs-common && apt-get clean && rm -rf /var/lib/apt/lists/*




USER manila