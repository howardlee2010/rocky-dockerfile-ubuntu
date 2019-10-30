FROM kolla/ubuntu-source-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="rabbitmq" build-date="20191030"








RUN usermod --append --home /var/lib/rabbitmq --groups kolla rabbitmq \
    && mkdir -p /var/lib/rabbitmq \
    && chown -R 42439:42439 /var/lib/rabbitmq




    

    
         
    

    
         

    



RUN apt-get update && apt-get -y install --no-install-recommends erlang-nox logrotate erlang-base-hipe && apt-get clean && rm -rf /var/lib/apt/lists/* && curl --location https://www.rabbitmq.com/releases/rabbitmq-server/v3.6.5/rabbitmq-server_3.6.5-1_all.deb -o rabbitmq-server_3.6.5-1_all.deb && dpkg -i rabbitmq-server_3.6.5-1_all.deb && rm -rf rabbitmq-server_3.6.5-1_all.deb





RUN rm -rf /var/lib/rabbitmq/* \
    && ln -s /usr/lib/rabbitmq/lib/rabbitmq_server-3.6.* /usr/lib/rabbitmq/lib/rabbitmq_server-3.6 \
    && curl -o /usr/lib/rabbitmq/lib/rabbitmq_server-3.6/plugins/rabbitmq_clusterer-3.6.x-667f92b0.ez https://www.rabbitmq.com/community-plugins/v3.6.x/rabbitmq_clusterer-3.6.x-667f92b0.ez \
    && /usr/lib/rabbitmq/bin/rabbitmq-plugins enable --offline \
       rabbitmq_management \
       rabbitmq_clusterer



COPY extend_start.sh /usr/local/bin/kolla_extend_start
COPY rabbitmq_get_gospel_node.py /usr/local/bin/rabbitmq_get_gospel_node
RUN chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/rabbitmq_get_gospel_node




USER rabbitmq