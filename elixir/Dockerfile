FROM outstand/elixir:1.7.3-alpine

RUN apk add --no-cache socat \
      && cd /srv \
      && wget https://github.com/JakeBecker/elixir-ls/releases/download/v0.2.24/elixir-ls.zip \
      && unzip elixir-ls.zip \
      && rm elixir-ls.zip \
      && chmod +x language_server.sh

EXPOSE 7659
CMD ["socat", "-d", "-d", "TCP4-LISTEN:7659,reuseaddr,fork", "EXEC:/srv/language_server.sh"]
