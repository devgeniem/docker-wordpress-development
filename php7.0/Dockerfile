FROM devgeniem/wordpress-server:latest
MAINTAINER Onni Hakala - Geniem Oy. <onni.hakala@geniem.com>

# Install xdebug
RUN apk add --update-cache --repository http://dl-4.alpinelinux.org/alpine/edge/testing/ \
    php7-xdebug php7-mongodb php7-mcrypt && \

    # Add inotify tools for quicker loading
    apk add inotify-tools && \

    # Add mcrypt
    apk add libmcrypt-dev && \

    # Remove cache and tmp files
    rm -rf /var/cache/apk/* && \
    rm -rf /tmp/* && \

    # Create folder for xdebug
    mkdir /tmp/xdebug/

# Copy our development changes
COPY etc/ /etc/
