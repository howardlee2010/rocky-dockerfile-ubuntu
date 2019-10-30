FROM kolla/ubuntu-source-nova-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="nova-compute-ironic" build-date="20191030"









RUN apt-get update && apt-get -y install --no-install-recommends genisoimage && apt-get clean && rm -rf /var/lib/apt/lists/*






USER nova