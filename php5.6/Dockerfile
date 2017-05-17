FROM devgeniem/wordpress-server:php5.6
MAINTAINER Onni Hakala - Geniem Oy. <onni.hakala@geniem.com>

ENV \
    # Directory to store xdebug profiling
    XDEBUG_PROFILER_DIR="/tmp/xdebug" \
    # Use OSX IP address loopback hack: https://gist.githubusercontent.com/ralphschindler/535dc5916ccbd06f53c1b0ee5a868c93/raw/com.ralphschindler.docker_10254_alias.plist
    # This can be overridden by you
    XDEBUG_REMOTE_HOST="10.254.254.254" \
    XDEBUG_REMOTE_PORT="9000" \
    # Web user and group
    WEB_USER="wordpress" \
    WEB_GROUP="web"

# Install xdebug
RUN apk add --no-cache --repository http://dl-4.alpinelinux.org/alpine/edge/testing/ \
    php5-xdebug && \

    # Remove cache and tmp files
    rm -rf /var/cache/apk/* && \
    rm -rf /tmp/* && \

    # Create folder for xdebug
    mkdir /tmp/xdebug/

# Copy our development changes
COPY etc/ /etc/
