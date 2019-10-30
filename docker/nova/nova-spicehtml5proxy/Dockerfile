FROM kolla/ubuntu-source-nova-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="nova-spicehtml5proxy" build-date="20191030"






    

        

    


RUN apt-get update && apt-get -y install --no-install-recommends spice-html5 websockify && apt-get clean && rm -rf /var/lib/apt/lists/*




USER nova