FROM kolla/ubuntu-source-ovn-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ovn-northd" build-date="20191030"






    


RUN apt-get update && apt-get -y install --no-install-recommends ovn-central && apt-get clean && rm -rf /var/lib/apt/lists/*


