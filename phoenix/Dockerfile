FROM edevil/elixir:latest

MAINTAINER André Cruz <andre@cabine.org>

ENV PHOENIX_VERSION 1.1.2

RUN curl -sL https://deb.nodesource.com/setup_5.x | bash -

RUN apt-get install -y nodejs

RUN mix archive.install https://github.com/phoenixframework/phoenix/releases/download/v$PHOENIX_VERSION/phoenix_new-$PHOENIX_VERSION.ez --force
