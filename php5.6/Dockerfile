FROM devgeniem/wordpress-server:php5.6
MAINTAINER Onni Hakala - Geniem Oy. <onni.hakala@geniem.com>

ENV \
    # Directory to store xdebug profiling
    XDEBUG_PROFILER_DIR="/tmp/xdebug" \
    # This makes no sense before you override this with your machine ip instead
    XDEBUG_REMOTE_HOST="127.0.0.1" \
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
