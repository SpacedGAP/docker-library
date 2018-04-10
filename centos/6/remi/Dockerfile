FROM krallin/centos-tini:6

# Start as root
USER root

ENV LANGUAGE=en_US.UTF-8
ENV LC_ALL=en_US.UTF-8
ENV LC_CTYPE=en_US.UTF-8
ENV LANG=en_US.UTF-8
ENV TERM xterm

# Update and Install EPEL and Remi Repos
RUN yum -y update && \
    yum -y install \
        https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm \
        https://rpms.remirepo.net/enterprise/remi-release-6.rpm \
    && \
    yum clean all && \
    rm -rf \
        /var/cache/* \
        /tmp/* \
        /var/tmp/*

ENTRYPOINT ["/usr/bin/tini", "--"]

CMD ["/bin/bash"]
