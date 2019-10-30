FROM kolla/ubuntu-source-nova-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="nova-novncproxy" build-date="20191030"







        



RUN apt-get update && apt-get -y install --no-install-recommends novnc && apt-get clean && rm -rf /var/lib/apt/lists/*




USER nova