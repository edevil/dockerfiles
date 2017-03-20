FROM microsoft/oms
MAINTAINER André Cruz "andre@cabine.org"

# Disable prompts from apt.
ENV DEBIAN_FRONTEND noninteractive

# Install prerequisites.
RUN apt-get update && \
    apt-get install -y -q make g++ && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install the Fluentd plug-ins.
RUN /opt/microsoft/omsagent/ruby/bin/fluent-gem install fluent-plugin-kubernetes_metadata_filter
