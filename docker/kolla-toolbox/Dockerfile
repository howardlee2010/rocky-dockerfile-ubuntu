FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="kolla-toolbox" build-date="20191030"











RUN usermod --append --home /var/lib/ansible --groups kolla ansible \
    && mkdir -p /var/lib/ansible \
    && chown -R 42401:42401 /var/lib/ansible



    

    
         
    
    # Debian/stretch ships libmysqlclient.so in separate package
    


RUN apt-get update && apt-get -y install --no-install-recommends build-essential ca-certificates crudini gdisk git jq libffi-dev libssl-dev libxslt1-dev mariadb-client python-dev libmariadbclient-dev && apt-get clean && rm -rf /var/lib/apt/lists/*


RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py \
    && python get-pip.py \
    && rm get-pip.py




RUN pip --no-cache-dir install --upgrade virtualenv \
    && virtualenv --system-site-packages /opt/ansible

ENV PATH /opt/ansible/bin:$PATH



RUN pip --no-cache-dir install --upgrade ansible==2.2.0.0 "cmd2<0.9.0" influxdb MySQL-python os-client-config==1.29.0 pbr==4.0.0 pymongo python-openstackclient==3.14.0 pytz pyudev shade==1.27.1 \
    && mkdir -p /etc/ansible /usr/share/ansible \
    && echo 'localhost ansible_connection=local ansible_python_interpreter=/opt/ansible/bin/python' > /etc/ansible/hosts \
    && sed -i 's|  "identity_api_version": "2.0",|  "identity_api_version": "3",|' /opt/ansible/lib/python2.7/site-packages/os_client_config/defaults.json

ENV ANSIBLE_LIBRARY /usr/share/ansible:$ANSIBLE_LIBRARY

COPY find_disks.py kolla_keystone_service.py kolla_keystone_user.py kolla_sanity.py /usr/share/ansible/
COPY ansible.cfg /var/lib/ansible/.ansible.cfg

COPY ansible_sudoers /etc/sudoers.d/kolla_ansible_sudoers
RUN chmod 440 /etc/sudoers.d/kolla_ansible_sudoers




USER ansible