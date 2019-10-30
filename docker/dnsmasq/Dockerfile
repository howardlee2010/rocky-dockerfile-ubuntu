FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="dnsmasq" build-date="20191030"






RUN apt-get update && apt-get -y install --no-install-recommends dnsmasq && apt-get clean && rm -rf /var/lib/apt/lists/*


