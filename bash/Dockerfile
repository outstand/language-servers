FROM python:2-alpine

RUN apk add --no-cache nodejs npm build-base socat \
      && npm i --unsafe-perm -g bash-language-server

EXPOSE 7661
CMD ["socat", "-d", "-d", "TCP4-LISTEN:7661,reuseaddr,fork", "EXEC:bash-language-server start"]
