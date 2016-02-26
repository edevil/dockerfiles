FROM edevil/elixir:latest

MAINTAINER André Cruz <andre@cabine.org>

RUN curl -sL https://deb.nodesource.com/setup_5.x | bash -

RUN apt-get update && apt-get install -y nodejs gcc

RUN mix archive.install https://github.com/phoenixframework/archives/raw/master/phoenix_new.ez --force
