FROM kolla/ubuntu-source-cinder-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="cinder-api" build-date="20191030"







    
        
RUN apt-get update && apt-get -y install --no-install-recommends apache2 libapache2-mod-wsgi && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN echo > /etc/apache2/ports.conf

    

RUN mkdir -p /var/www/cgi-bin/cinder \
    && cp -a /var/lib/kolla/venv/bin/cinder-wsgi /var/www/cgi-bin/cinder/cinder-wsgi



COPY extend_start.sh /usr/local/bin/kolla_cinder_extend_start
RUN chmod 755 /usr/local/bin/kolla_cinder_extend_start \
    && chown -R cinder: /var/www/cgi-bin/cinder \
    && chmod 755 /var/www/cgi-bin/cinder/cinder-wsgi


