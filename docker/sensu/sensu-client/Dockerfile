FROM kolla/ubuntu-source-sensu-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="sensu-client" build-date="20191030"






    
    
        
    


RUN apt-get update && apt-get -y install --no-install-recommends build-essential ceph-common inetutils-ping libsasl2-dev mysql-client ntp python-pymongo docker.io && apt-get clean && rm -rf /var/lib/apt/lists/*



# Sensu plugins are all using semantic versioning.
# Let's cap them to the known major version that works with the ruby shipped on
# rhel/centos/oraclelinux (currently 2.0)


# TODO(mandre) Use packaged sensu plugins from centos-opstools for binary distro
# http://cbs.centos.org/koji/search?match=glob&type=package&terms=*sensu*
# NOTE(hrw): whois 5.0.0 requires Ruby 2.4+ while CentOS has 2.0
# NOTE(yoctozepto): pinning minitest for the same reason
RUN  sensu-install --plugins ceph:"~>1",cpu-checks:"~>1",disk-checks:"~>2",dns:"~>1",docker:"~>3",elasticsearch:"~>1",filesystem-checks:"~>1",haproxy:"~>1",http:"~>1",io-checks:"~>1",load-checks:"~>3",memcached:"~>0",memory-checks:"~>1",mongodb:"~>0",mysql:"~>2",network-checks:"~>2",ntp:"~>1",openstack:"~>1",process-checks:"~>2",rabbitmq:"~>3",redis:"~>2",uptime-checks:"~>1",vmstats:"~>1"



