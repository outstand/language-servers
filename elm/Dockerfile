FROM haskell:latest

RUN cd /srv \
      && git clone https://github.com/elm-tooling/elm-language-server .\
      && git submodule update --init --recursive \
      && stack setup \
      && stack install

RUN apt-get update && apt-get install -y --no-install-recommends \
    socat \
  && rm -rf /var/lib/apt/lists/*

EXPOSE 7660
CMD ["socat", "-d", "-d", "TCP4-LISTEN:7660,reuseaddr,fork", "EXEC:elm-language-server"]
