FROM devgeniem/wordpress-server:php5.6
MAINTAINER Onni Hakala - Geniem Oy. <onni.hakala@geniem.com>

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
