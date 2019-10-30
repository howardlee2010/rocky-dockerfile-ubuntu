FROM kolla/ubuntu-source-nova-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="nova-api" build-date="20191030"







    

        

RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN echo > /etc/apache2/ports.conf

    



COPY extend_start.sh /usr/local/bin/kolla_nova_extend_start
RUN chmod 755 /usr/local/bin/kolla_nova_extend_start




USER nova