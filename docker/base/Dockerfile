FROM ubuntu:18.04
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="base" build-date="20191030"



RUN groupadd --force --gid 42475 almanach \
    && useradd -M --shell /usr/sbin/nologin --uid 42475 --gid 42475 almanach \
    && groupadd --force --gid 42401 ansible \
    && useradd -M --shell /usr/sbin/nologin --uid 42401 --gid 42401 ansible \
    && groupadd --force --gid 42402 aodh \
    && useradd -M --shell /usr/sbin/nologin --uid 42402 --gid 42402 aodh \
    && groupadd --force --gid 42403 barbican \
    && useradd -M --shell /usr/sbin/nologin --uid 42403 --gid 42403 barbican \
    && groupadd --force --gid 42404 bifrost \
    && useradd -M --shell /usr/sbin/nologin --uid 42404 --gid 42404 bifrost \
    && groupadd --force --gid 42471 blazar \
    && useradd -M --shell /usr/sbin/nologin --uid 42471 --gid 42471 blazar \
    && groupadd --force --gid 42405 ceilometer \
    && useradd -M --shell /usr/sbin/nologin --uid 42405 --gid 42405 ceilometer \
    && groupadd --force --gid 64045 ceph \
    && useradd -M --shell /usr/sbin/nologin --uid 64045 --gid 64045 ceph \
    && groupadd --force --gid 42406 chrony \
    && useradd -M --shell /usr/sbin/nologin --uid 42406 --gid 42406 chrony \
    && groupadd --force --gid 42407 cinder \
    && useradd -M --shell /usr/sbin/nologin --uid 42407 --gid 42407 cinder \
    && groupadd --force --gid 42408 cloudkitty \
    && useradd -M --shell /usr/sbin/nologin --uid 42408 --gid 42408 cloudkitty \
    && groupadd --force --gid 42409 collectd \
    && useradd -M --shell /usr/sbin/nologin --uid 42409 --gid 42409 collectd \
    && groupadd --force --gid 42410 congress \
    && useradd -M --shell /usr/sbin/nologin --uid 42410 --gid 42410 congress \
    && groupadd --force --gid 42411 designate \
    && useradd -M --shell /usr/sbin/nologin --uid 42411 --gid 42411 designate \
    && groupadd --force --gid 42464 dragonflow \
    && useradd -M --shell /usr/sbin/nologin --uid 42464 --gid 42464 dragonflow \
    && groupadd --force --gid 42466 ec2api \
    && useradd -M --shell /usr/sbin/nologin --uid 42466 --gid 42466 ec2api \
    && groupadd --force --gid 42412 elasticsearch \
    && useradd -M --shell /usr/sbin/nologin --uid 42412 --gid 42412 elasticsearch \
    && groupadd --force --gid 42413 etcd \
    && useradd -M --shell /usr/sbin/nologin --uid 42413 --gid 42413 etcd \
    && groupadd --force --gid 42474 fluentd \
    && useradd -M --shell /usr/sbin/nologin --uid 42474 --gid 42474 fluentd \
    && groupadd --force --gid 42414 freezer \
    && useradd -M --shell /usr/sbin/nologin --uid 42414 --gid 42414 freezer \
    && groupadd --force --gid 42415 glance \
    && useradd -M --shell /usr/sbin/nologin --uid 42415 --gid 42415 glance \
    && groupadd --force --gid 42416 gnocchi \
    && useradd -M --shell /usr/sbin/nologin --uid 42416 --gid 42416 gnocchi \
    && groupadd --force --gid 42417 grafana \
    && useradd -M --shell /usr/sbin/nologin --uid 42417 --gid 42417 grafana \
    && groupadd --force --gid 42454 haproxy \
    && useradd -M --shell /usr/sbin/nologin --uid 42454 --gid 42454 haproxy \
    && groupadd --force --gid 42418 heat \
    && useradd -M --shell /usr/sbin/nologin --uid 42418 --gid 42418 heat \
    && groupadd --force --gid 42420 horizon \
    && useradd -M --shell /usr/sbin/nologin --uid 42420 --gid 42420 horizon \
    && groupadd --force --gid 42477 hugetlbfs \
    && useradd -M --shell /usr/sbin/nologin --uid 42477 --gid 42477 hugetlbfs \
    && groupadd --force --gid 42421 influxdb \
    && useradd -M --shell /usr/sbin/nologin --uid 42421 --gid 42421 influxdb \
    && groupadd --force --gid 42422 ironic \
    && useradd -M --shell /usr/sbin/nologin --uid 42422 --gid 42422 ironic \
    && groupadd --force --gid 42461 ironic-inspector \
    && useradd -M --shell /usr/sbin/nologin --uid 42461 --gid 42461 ironic-inspector \
    && groupadd --force --gid 42423 kafka \
    && useradd -M --shell /usr/sbin/nologin --uid 42423 --gid 42423 kafka \
    && groupadd --force --gid 42458 karbor \
    && useradd -M --shell /usr/sbin/nologin --uid 42458 --gid 42458 karbor \
    && groupadd --force --gid 42425 keystone \
    && useradd -M --shell /usr/sbin/nologin --uid 42425 --gid 42425 keystone \
    && groupadd --force --gid 42426 kibana \
    && useradd -M --shell /usr/sbin/nologin --uid 42426 --gid 42426 kibana \
    && groupadd --force --gid 42400 kolla \
    && useradd -M --shell /usr/sbin/nologin --uid 42400 --gid 42400 kolla \
    && groupadd --force --gid 42469 kuryr \
    && useradd -M --shell /usr/sbin/nologin --uid 42469 --gid 42469 kuryr \
    && groupadd --force --gid 42473 libvirt \
    && useradd -M --shell /usr/sbin/nologin --uid 42473 --gid 42473 libvirt \
    && groupadd --force --gid 42478 logstash \
    && useradd -M --shell /usr/sbin/nologin --uid 42478 --gid 42478 logstash \
    && groupadd --force --gid 42428 magnum \
    && useradd -M --shell /usr/sbin/nologin --uid 42428 --gid 42428 magnum \
    && groupadd --force --gid 42429 manila \
    && useradd -M --shell /usr/sbin/nologin --uid 42429 --gid 42429 manila \
    && groupadd --force --gid 42457 memcached \
    && useradd -M --shell /usr/sbin/nologin --uid 42457 --gid 42457 memcached \
    && groupadd --force --gid 42430 mistral \
    && useradd -M --shell /usr/sbin/nologin --uid 42430 --gid 42430 mistral \
    && groupadd --force --gid 42431 monasca \
    && useradd -M --shell /usr/sbin/nologin --uid 42431 --gid 42431 monasca \
    && groupadd --force --gid 65534 mongodb \
    && useradd -M --shell /usr/sbin/nologin --uid 42432 --gid 65534 mongodb \
    && groupadd --force --gid 42433 murano \
    && useradd -M --shell /usr/sbin/nologin --uid 42433 --gid 42433 murano \
    && groupadd --force --gid 42434 mysql \
    && useradd -M --shell /usr/sbin/nologin --uid 42434 --gid 42434 mysql \
    && groupadd --force --gid 42435 neutron \
    && useradd -M --shell /usr/sbin/nologin --uid 42435 --gid 42435 neutron \
    && groupadd --force --gid 42436 nova \
    && useradd -M --shell /usr/sbin/nologin --uid 42436 --gid 42436 nova \
    && groupadd --force --gid 42470 novajoin \
    && useradd -M --shell /usr/sbin/nologin --uid 42470 --gid 42470 novajoin \
    && groupadd --force --gid 42437 octavia \
    && useradd -M --shell /usr/sbin/nologin --uid 42437 --gid 42437 octavia \
    && groupadd --force --gid 42462 odl \
    && useradd -M --shell /usr/sbin/nologin --uid 42462 --gid 42462 odl \
    && groupadd --force --gid 42476 openvswitch \
    && useradd -M --shell /usr/sbin/nologin --uid 42476 --gid 42476 openvswitch \
    && groupadd --force --gid 42438 panko \
    && useradd -M --shell /usr/sbin/nologin --uid 42438 --gid 42438 panko \
    && groupadd --force --gid 42472 prometheus \
    && useradd -M --shell /usr/sbin/nologin --uid 42472 --gid 42472 prometheus \
    && groupadd --force --gid 42465 qdrouterd \
    && useradd -M --shell /usr/sbin/nologin --uid 42465 --gid 42465 qdrouterd \
    && groupadd --force --gid 42427 qemu \
    && useradd -M --shell /usr/sbin/nologin --uid 42427 --gid 42427 qemu \
    && groupadd --force --gid 42439 rabbitmq \
    && useradd -M --shell /usr/sbin/nologin --uid 42439 --gid 42439 rabbitmq \
    && groupadd --force --gid 42440 rally \
    && useradd -M --shell /usr/sbin/nologin --uid 42440 --gid 42440 rally \
    && groupadd --force --gid 42460 redis \
    && useradd -M --shell /usr/sbin/nologin --uid 42460 --gid 42460 redis \
    && groupadd --force --gid 42441 sahara \
    && useradd -M --shell /usr/sbin/nologin --uid 42441 --gid 42441 sahara \
    && groupadd --force --gid 42442 searchlight \
    && useradd -M --shell /usr/sbin/nologin --uid 42442 --gid 42442 searchlight \
    && groupadd --force --gid 42443 senlin \
    && useradd -M --shell /usr/sbin/nologin --uid 42443 --gid 42443 senlin \
    && groupadd --force --gid 42467 sensu \
    && useradd -M --shell /usr/sbin/nologin --uid 42467 --gid 42467 sensu \
    && groupadd --force --gid 42468 skydive \
    && useradd -M --shell /usr/sbin/nologin --uid 42468 --gid 42468 skydive \
    && groupadd --force --gid 42444 solum \
    && useradd -M --shell /usr/sbin/nologin --uid 42444 --gid 42444 solum \
    && groupadd --force --gid 42479 storm \
    && useradd -M --shell /usr/sbin/nologin --uid 42479 --gid 42479 storm \
    && groupadd --force --gid 42445 swift \
    && useradd -M --shell /usr/sbin/nologin --uid 42445 --gid 42445 swift \
    && groupadd --force --gid 42446 tacker \
    && useradd -M --shell /usr/sbin/nologin --uid 42446 --gid 42446 tacker \
    && groupadd --force --gid 42447 td-agent \
    && useradd -M --shell /usr/sbin/nologin --uid 42447 --gid 42447 td-agent \
    && groupadd --force --gid 42448 telegraf \
    && useradd -M --shell /usr/sbin/nologin --uid 42448 --gid 42448 telegraf \
    && groupadd --force --gid 42480 tempest \
    && useradd -M --shell /usr/sbin/nologin --uid 42480 --gid 42480 tempest \
    && groupadd --force --gid 42449 trove \
    && useradd -M --shell /usr/sbin/nologin --uid 42449 --gid 42449 trove \
    && groupadd --force --gid 42459 vitrage \
    && useradd -M --shell /usr/sbin/nologin --uid 42459 --gid 42459 vitrage \
    && groupadd --force --gid 42450 vmtp \
    && useradd -M --shell /usr/sbin/nologin --uid 42450 --gid 42450 vmtp \
    && groupadd --force --gid 42451 watcher \
    && useradd -M --shell /usr/sbin/nologin --uid 42451 --gid 42451 watcher \
    && groupadd --force --gid 42452 zaqar \
    && useradd -M --shell /usr/sbin/nologin --uid 42452 --gid 42452 zaqar \
    && groupadd --force --gid 42453 zookeeper \
    && useradd -M --shell /usr/sbin/nologin --uid 42453 --gid 42453 zookeeper \
    && groupadd --force --gid 42463 zun \
    && useradd -M --shell /usr/sbin/nologin --uid 42463 --gid 42463 zun

LABEL kolla_version="7.0.5"




ENV KOLLA_BASE_DISTRO=ubuntu \
    KOLLA_INSTALL_TYPE=source \
    KOLLA_INSTALL_METATYPE=mixed

#### Customize PS1 to be used with bash shell
COPY kolla_bashrc /tmp/
RUN cat /tmp/kolla_bashrc >> /etc/skel/.bashrc \
    && cat /tmp/kolla_bashrc >> /root/.bashrc

# PS1 var when used /bin/sh shell
ENV PS1="$(tput bold)($(printenv KOLLA_SERVICE_NAME))$(tput sgr0)[$(id -un)@$(hostname -s) $(pwd)]$ "



RUN if [ $(awk -F '=' '/DISTRIB_RELEASE/{print $2}' /etc/lsb-release) != "18.04" ]; then \
        echo "Only release '18.04' is supported on ubuntu"; false; fi

# Customize PS1 bash shell
RUN cat /tmp/kolla_bashrc >> /etc/bash.bashrc

# This will prevent questions from being asked during the install
ENV DEBIAN_FRONTEND noninteractive

# Reducing disk footprint
COPY dpkg_reducing_disk_footprint /etc/dpkg/dpkg.cfg.d/dpkg_reducing_disk_footprint


# Need apt-transport-https and ca-certificates before replacing sources.list or
# apt-get update will not work if any repositories are accessed via HTTPS

RUN apt-get update && apt-get -y install --no-install-recommends apt-transport-https ca-certificates curl dirmngr gnupg && apt-get clean && rm -rf /var/lib/apt/lists/*




COPY sources.list.ubuntu /etc/apt/sources.list




COPY apt_preferences.ubuntu /etc/apt/preferences









    
    
    
    
    
    
    
    
    
    
    
    



        RUN apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 05CE15085FC09D18E99EFB22684A14CF2582E0C5 \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 177F4010FE56CA3336300305F1656F24C74CD1D8 \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 391A9AA2147192839E9DB0315EDB1B62EC4926EA \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 46095ACC8548582C1A2699A9D27D666CD88E42B4 \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 49B07274951063870A8B7EAE7B8AA1A344C05248 \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 4D1BB29D63D98E422B2113B19334A25F8507EFA5 \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 58118E89F3A912897C070ADBF76221572C52609D \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 4D8EB5FDA37AB55F41A135203BF88A0C6A770882 \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 901F9177AB97ACBE \
             && apt-key adv --no-tty --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 A20F259AEB9C94BB
         RUN curl https://packages.grafana.com/gpg.key | apt-key add -
    
RUN apt-get update \
    && apt-get -y upgrade \
    && apt-get -y dist-upgrade \
    && apt-get -y install --no-install-recommends \
        apt-utils \
        curl \
        gawk \
        iproute2 \
        kmod \
        lvm2 \
        netbase \
        open-iscsi \
        python \
        socat \
        sudo \
        tgt \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*



RUN sed -i \
        -e "s|\('purelib': '\$base/\)local/\(lib/python\$py_version_short/dist-packages',\)|\1\2|" \
        -e "s|\('platlib': '\$platbase/\)local/\(lib/python\$py_version_short/dist-packages',\)|\1\2|" \
        -e "s|\('headers': '\$base/\)local/\(include/python\$py_version_short/\$dist_name',\)|\1\2|" \
        -e "s|\('scripts': '\$base/\)local/\(bin',\)|\1\2|" \
        -e "s|\('data'   : '\$base\)/local\(',\)|\1\2|" \
        /usr/lib/python2.7/distutils/command/install.py \
    && rm -rf /usr/lib/python2.7/site-packages \
    && ln -s dist-packages /usr/lib/python2.7/site-packages





COPY set_configs.py /usr/local/bin/kolla_set_configs
COPY start.sh /usr/local/bin/kolla_start
COPY sudoers /etc/sudoers
COPY curlrc /root/.curlrc






RUN curl -sSL https://github.com/Yelp/dumb-init/releases/download/v1.1.3/dumb-init_1.1.3_amd64 -o /usr/local/bin/dumb-init \
    && chmod +x /usr/local/bin/dumb-init



ENTRYPOINT ["dumb-init", "--single-child", "--"]




RUN touch /usr/local/bin/kolla_extend_start \
    && chmod 755 /usr/local/bin/kolla_start /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_set_configs \
    && chmod 440 /etc/sudoers \
    && mkdir -p /var/log/kolla \
    && chown :kolla /var/log/kolla \
    && chmod 2775 /var/log/kolla \
    && rm -f /tmp/kolla_bashrc


CMD ["kolla_start"]