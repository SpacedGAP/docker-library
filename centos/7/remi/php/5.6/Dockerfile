FROM spacedgap/centos:7-remi

# Start as root
USER root

RUN yum-config-manager --enable remi-php56 && \
    yum clean all && \
    rm -rf \
        /var/cache/* \
        /tmp/* \
        /var/tmp/*

ENTRYPOINT ["/usr/bin/tini", "--"]

CMD ["/bin/bash"]
