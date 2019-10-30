FROM kolla/ubuntu-source-rsyslog-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="rsyslog" build-date="20191030"






    


RUN apt-get update && apt-get -y install --no-install-recommends rsyslog-gnutls && apt-get clean && rm -rf /var/lib/apt/lists/*


