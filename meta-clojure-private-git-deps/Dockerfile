FROM clojure:tools-deps-alpine
RUN apk add --no-cache openssh-client

# Authorize SSH Host
RUN mkdir -p /root/.ssh && \
    chmod 0700 /root/.ssh && \
    ssh-keyscan gitlab.com >> /root/.ssh/known_hosts && \
    ssh-keyscan bitbucket.com >> /root/.ssh/known_hosts && \
    ssh-keyscan github.com >> /root/.ssh/known_hosts

# Create a wrapper for clojure binary
RUN mkdir -p /usr/local/sbin/ && \
    echo -e '#!/bin/sh \n eval $(ssh-agent -s) && ssh-add -k ~/.ssh/id_rsa && exec /usr/local/bin/clojure "$@"' >> /usr/local/sbin/clojure && \
    chmod +x /usr/local/sbin/clojure

ARG ssh_prv_key
ARG ssh_pub_key

# Add the keys and set permissions
RUN echo "$ssh_prv_key" > /root/.ssh/id_rsa && \
    echo "$ssh_pub_key" > /root/.ssh/id_rsa.pub && \
    chmod 600 /root/.ssh/id_rsa && \
    chmod 600 /root/.ssh/id_rsa.pub
