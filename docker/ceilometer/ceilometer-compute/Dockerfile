FROM kolla/ubuntu-source-ceilometer-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="ceilometer-compute" build-date="20191030"






    
        
    

RUN apt-get update && apt-get -y install --no-install-recommends python-libvirt && apt-get clean && rm -rf /var/lib/apt/lists/*

# NOTE(jeffrey4l): just for back compatibility


RUN true






# NOTE(huikang): non-root user does not work with libvirt.sock.
#                Need configuration in nova-libvirt container to allow
#                USER ceilometer to access libvirt.sock