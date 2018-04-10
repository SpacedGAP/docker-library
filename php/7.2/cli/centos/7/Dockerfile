FROM spacedgap/centos:7-remi-php7.2

# Install Libraries and Packages
RUN yum -y install \
        autoconf \
        dpkg-dev \
        file \
        gcc-c++ \
        gcc \
        glibc-devel \
        make \
        pkgconfig \
        re2c \
        ca-certificates \
        curl \
        tar \
        xz \
        openssl \
        wget \
        libargon2-devel \
        libedit-devel \
        libsodium-devel \
        libsqlite3x-devel \
        openssl-devel \
        libxml2-devel \
        zlib-devel \
        # PHP
        php-cli \
        php-common \
        php-pear \
        php-mbstring \
        php-mysqlnd \
        php-pdo \
        php-pecl-jsonc \
        php-pecl-zip \
        php-process \
        php-xml

RUN pecl update-channels

# Clean up
RUN yum clean all && \
    rm -rf \
        /var/cache/* \
        /tmp/* \
        /var/tmp/*

COPY ./scripts/entrypoint/docker-php-entrypoint /usr/local/bin/

ENTRYPOINT ["/usr/bin/tini", "--", "docker-php-entrypoint"]

CMD ["php", "-a"]
