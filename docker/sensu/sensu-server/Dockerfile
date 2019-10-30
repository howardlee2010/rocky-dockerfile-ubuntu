FROM kolla/ubuntu-source-sensu-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="sensu-server" build-date="20191030"






    


RUN apt-get update && apt-get -y install --no-install-recommends build-essential libsasl2-dev && apt-get clean && rm -rf /var/lib/apt/lists/*



# Sensu plugins are all using semantic versioning.
# Let's cap them to the known major version that works with the ruby shipped on
# rhel/centos/oraclelinux (currently 2.0)


RUN sensu-install --plugins mailer:"~>3",slack:"~>3"





USER sensu