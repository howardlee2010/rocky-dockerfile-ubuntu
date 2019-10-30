FROM kolla/ubuntu-source-zun-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="zun-compute" build-date="20191030"









RUN apt-get update && apt-get -y install --no-install-recommends pciutils && apt-get clean && rm -rf /var/lib/apt/lists/*




USER zun