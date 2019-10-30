FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="kubetoolbox" build-date="20191030"







RUN apt-get update && apt-get -y install --no-install-recommends ceph-common ipmitool jq && apt-get clean && rm -rf /var/lib/apt/lists/*


    
    
        ENV KUBE_ARCH=amd64
    

    RUN curl -o /usr/bin/kubectl http://storage.googleapis.com/kubernetes-release/release/v1.5.4/bin/linux/${KUBE_ARCH}/kubectl \
        && chmod 755 /usr/bin/kubectl




