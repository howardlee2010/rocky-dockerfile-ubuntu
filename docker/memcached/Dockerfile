FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="memcached" build-date="20191030"







RUN usermod --append --home /run/memcache --groups kolla memcached \
    && mkdir -p /run/memcache \
    && chown -R 42457:42457 /run/memcache



RUN apt-get update && apt-get -y install --no-install-recommends memcached && apt-get clean && rm -rf /var/lib/apt/lists/*




USER memcached