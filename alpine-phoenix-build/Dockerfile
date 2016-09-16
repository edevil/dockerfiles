FROM alpine:edge
MAINTAINER André Cruz

RUN apk --update add erlang erlang-crypto erlang-sasl erlang-dev erlang-parsetools erlang-syntax-tools gettext make gcc g++ libgcc libstdc++ nodejs elixir git && rm -rf /var/cache/apk/*

RUN mix local.hex --force && mix local.rebar --force

CMD ["/bin/sh"]
