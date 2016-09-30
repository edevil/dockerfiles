# Copyright 2016 The Kubernetes Authors.

FROM ubuntu:16.04
MAINTAINER André Cruz "andre@cabine.org"

# Ensure there are enough file descriptors for running Fluentd.
RUN ulimit -n 65536

# Disable prompts from apt.
ENV DEBIAN_FRONTEND noninteractive

# Install prerequisites.
RUN apt-get update && \
    apt-get install -y -q curl make g++ sudo && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install Fluentd.
RUN /usr/bin/curl -L https://td-toolbelt.herokuapp.com/sh/install-ubuntu-xenial-td-agent2.sh | sh

# Change the default user and group to root.
# Needed to allow access to /var/log/docker/... files.
RUN sed -i -e "s/USER=td-agent/USER=root/" -e "s/GROUP=td-agent/GROUP=root/" /etc/init.d/td-agent

# Install the Fluentd plug-ins.
RUN td-agent-gem install fluent-plugin-kubernetes_metadata_filter fluent-plugin-elasticsearch fluent-plugin-logentries fluent-plugin-logzio

# Copy the Fluentd configuration file.
# COPY td-agent.conf /etc/td-agent/td-agent.conf
# Instead the configuration file will be exposed via configmap.

# Run the Fluentd service.
ENTRYPOINT ["td-agent"]
