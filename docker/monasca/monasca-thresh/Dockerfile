FROM kolla/ubuntu-source-storm:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="monasca-thresh" build-date="20191030"

USER root








RUN usermod --append --home /var/lib/monasca --groups kolla monasca \
    && mkdir -p /var/lib/monasca \
    && chown -R 42431:42431 /var/lib/monasca





    


ARG java_arch=amd64


ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-${java_arch}/



RUN apt-get update && apt-get -y install --no-install-recommends openjdk-8-jdk-headless maven && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD monasca-thresh-archive /monasca-thresh-source
ADD additions/monasca-common* /monasca-common-source





# FIXME(dszumski): Remove this when the following bug is fixed:
# https://bugs.launchpad.net/ubuntu/+source/ca-certificates-java/+bug/1770553




RUN cd /monasca-common-source/java \
    && mvn clean install -DskipTests -Djavax.net.ssl.trustStorePassword=changeit \
    && cd /monasca-thresh-source/monasca-thresh-*/thresh \
    && mvn clean package -DskipTests -Djavax.net.ssl.trustStorePassword=changeit




# Overwrite the script inherited from Storm
COPY extend_start.sh /usr/local/bin/kolla_extend_start
RUN touch /usr/local/bin/kolla_monasca_extend_start \
    && chmod 755 /usr/local/bin/kolla_extend_start /usr/local/bin/kolla_monasca_extend_start




USER monasca