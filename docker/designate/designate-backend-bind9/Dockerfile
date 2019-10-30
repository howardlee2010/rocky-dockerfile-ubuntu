FROM kolla/ubuntu-source-designate-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="designate-backend-bind9" build-date="20191030"






   

RUN apt-get update && apt-get -y install --no-install-recommends bind9 && apt-get clean && rm -rf /var/lib/apt/lists/*





RUN mkdir -p /var/lib/kolla/ /var/lib/bind/ /run/bind \
     && chown -R root: /var/lib/bind /run/bind \
     && chmod 755 /run/bind


