FROM devgeniem/wordpress-server:debian-php7.0
MAINTAINER Onni Hakala - Geniem Oy. <onni.hakala@geniem.com>

ENV \
    # Directory to store xdebug profiling
    XDEBUG_PROFILER_DIR="/tmp/xdebug" \
    # Use OSX IP address loopback hack: https://gist.githubusercontent.com/ralphschindler/535dc5916ccbd06f53c1b0ee5a868c93/raw/com.ralphschindler.docker_10254_alias.plist
    # This can be overridden by you
    XDEBUG_REMOTE_HOST="10.254.254.254" \
    XDEBUG_REMOTE_PORT="9000"

# Install xdebug
RUN \

    # Install package from dotdeb
    apt-get update && \
    && apt-get install -y php7.0-xdebug \


    # Create folder for xdebug profiler
    && mkdir -p $XDEBUG_PROFILER_DIR \

    # Cleanup
    && apt-get clean \
    && apt-get autoremove \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/* /var/log/apt/*

# Copy our development changes
COPY etc/ /etc/
