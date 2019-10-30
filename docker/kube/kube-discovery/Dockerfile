FROM kolla/ubuntu-source-kube-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="kube-discovery" build-date="20191030"

ENV KUBERNETES_COMPONENT=kube-discovery




# To match upstream we load the binary to /usr/local/bin
RUN true \
    && curl -L ${KUBERNETES_DOWNLOAD_ROOT}/${KUBERNETES_COMPONENT} -o /usr/local/bin/${KUBERNETES_COMPONENT} \
    && chmod +x /usr/local/bin/${KUBERNETES_COMPONENT}


# Clear any customisation by Kolla to entrypoint & command
ENTRYPOINT []
CMD []


