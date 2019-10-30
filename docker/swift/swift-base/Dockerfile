FROM kolla/ubuntu-source-openstack-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="swift-base" build-date="20191030"








RUN usermod --append --home /var/lib/swift --groups kolla swift \
    && mkdir -p /var/lib/swift \
    && chown -R 42445:42445 /var/lib/swift



    
        
    

RUN apt-get update && apt-get -y install --no-install-recommends liberasurecode-dev netcat-openbsd rsync && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD swift-base-archive /swift-base-source



RUN ln -s swift-base-source/* swift \
    && pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt /swift \
    && mkdir -p /etc/swift /var/cache/swift \
    && cp -r /swift/etc/* /etc/swift/ \
    && chown -R swift: /etc/swift /var/cache/swift


COPY swift-rootwrap /var/lib/kolla/venv/bin/swift-rootwrap
COPY rootwrap.conf /etc/swift/rootwrap.conf
COPY swift_sudoers /etc/sudoers.d/kolla_swift_sudoers

RUN chmod 755 /var/lib/kolla/venv/bin/swift-rootwrap \
    && chmod 644 /etc/swift/rootwrap.conf \
    && sed -i 's|^exec_dirs.*|exec_dirs=/var/lib/kolla/venv/bin,/sbin,/usr/sbin,/bin,/usr/bin,/usr/local/bin,/usr/local/sbin|g' /etc/swift/rootwrap.conf \
    && chmod 750 /etc/sudoers.d \
    && chmod 440 /etc/sudoers.d/kolla_swift_sudoers \
    && mkdir -p /opt/swift

