FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="openstack-base" build-date="20191030"






    
        

        
             
        

        # Debian/stretch ships libmysqlclient.so in separate package
        # Debian/stretch uses OpenSSL 1.1 as default, we need 1.0.2 one
        
            
        
    

RUN apt-get update && apt-get -y install --no-install-recommends build-essential ca-certificates git libffi-dev libpq-dev libxml2-dev libxslt1-dev libyaml-dev libz-dev pkg-config python-dev zip libmariadbclient-dev libssl-dev && apt-get clean && rm -rf /var/lib/apt/lists/*


RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py \
    && python get-pip.py \
    && rm get-pip.py




ADD openstack-base-archive /openstack-base-source
RUN ln -s openstack-base-source/* /requirements \
    && mkdir -p /var/lib/kolla \
    && pip --no-cache-dir install --upgrade virtualenv \
    && virtualenv --system-site-packages /var/lib/kolla/venv

ENV PATH /var/lib/kolla/venv/bin:$PATH

RUN pip --no-cache-dir install --upgrade -c /requirements/upper-constraints.txt Babel Mako MarkupSafe Paste PasteDeploy PyYAML Routes SQLAlchemy Tempita WebOb alembic amqp anyjson aodhclient appdirs cachetools cliff cmd2 cryptography contextlib2 debtcollector decorator elasticsearch enum34 eventlet fasteners funcsigs functools32 futures futurist gnocchiclient greenlet iso8601 jinja2 jsonpatch jsonpointer jsonschema keystoneauth1 keystonemiddleware kombu monotonic msgpack-python MySQL-python netaddr netifaces os-client-config oslo.concurrency oslo.config oslo.context oslo.db oslo.i18n oslo.log oslo.messaging oslo.middleware oslo.policy oslo.serialization oslo.service oslo.utils oslo.vmware osprofiler pbr pika pika-pool prettytable pycadf pyinotify pymysql pyngus pyparsing python-barbicanclient python-cinderclient python-cloudkittyclient python-congressclient python-dateutil python-designateclient python-editor python-glanceclient python-heatclient python-ironicclient python-keystoneclient python-magnumclient python-manilaclient python-memcached python-mistralclient python-muranoclient python-neutronclient python-novaclient python-openstackclient python-qpid-proton python-saharaclient python-swiftclient python-troveclient python-vitrageclient python-zaqarclient pytz repoze.lru requests requestsexceptions retrying simplejson six sqlalchemy-migrate sqlparse stevedore tooz[consul,etcd,etcd3,etcd3gw,zake,redis,postgresql,mysql,zookeeper,memcached,ipc] unicodecsv warlock wrapt



