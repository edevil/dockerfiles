FROM ubuntu:latest

MAINTAINER André Cruz <andre@cabine.org>

# Elixir requires UTF-8
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

# update and install some software requirements
RUN apt-get update && apt-get upgrade -y && apt-get install -y curl wget git make

# download and install Erlang package
RUN wget http://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb \
 && dpkg -i erlang-solutions_1.0_all.deb \
 && apt-get update \
 && rm erlang-solutions_1.0_all.deb

# install erlang && elixir from package
RUN apt-get install -y erlang erlang-ssl erlang-inets elixir

# install package managers
RUN mix local.hex --force && mix local.rebar --force
