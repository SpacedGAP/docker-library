FROM spacedgap/centos:6-remi

# Start as root
USER root

RUN yum-config-manager --enable remi-php72 && \
    yum clean all && \
    rm -rf \
        /var/cache/* \
        /tmp/* \
        /var/tmp/*

ENTRYPOINT ["/usr/bin/tini", "--"]

CMD ["/bin/bash"]
