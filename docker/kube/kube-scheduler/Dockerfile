FROM kolla/ubuntu-source-kube-base:7.0.5
LABEL maintainer="Kolla Project (https://launchpad.net/kolla)" name="kube-scheduler" build-date="20191030"

ENV KUBERNETES_COMPONENT=kube-scheduler




RUN true \
    && curl -L ${KUBERNETES_DOWNLOAD_ROOT}/${KUBERNETES_COMPONENT} -o /usr/bin/${KUBERNETES_COMPONENT} \
    && chmod +x /usr/bin/${KUBERNETES_COMPONENT}


# Clear any customisation by Kolla to entrypoint & command
ENTRYPOINT []
CMD []


