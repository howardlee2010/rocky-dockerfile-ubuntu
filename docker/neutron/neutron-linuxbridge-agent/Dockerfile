FROM kolla/ubuntu-source-neutron-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="neutron-linuxbridge-agent" build-date="20191030"







    



RUN apt-get update && apt-get -y install --no-install-recommends bridge-utils ebtables && apt-get clean && rm -rf /var/lib/apt/lists/*




USER neutron