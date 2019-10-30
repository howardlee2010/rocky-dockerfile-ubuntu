FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="tgtd" build-date="20191030"






    

RUN apt-get update && apt-get -y install --no-install-recommends tgt && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN sed -i '1 i include /var/lib/cinder/volumes/*' /etc/tgt/targets.conf




