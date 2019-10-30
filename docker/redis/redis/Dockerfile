FROM kolla/ubuntu-source-redis-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="redis" build-date="20191030"






    

RUN apt-get update && apt-get -y install --no-install-recommends redis-server && apt-get clean && rm -rf /var/lib/apt/lists/*




USER redis