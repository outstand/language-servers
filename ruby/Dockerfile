FROM outstand/ruby-base:2.5.3

RUN gem install solargraph

RUN solargraph download-core 2.5.1 && \
      solargraph download-core 2.4.4

EXPOSE 7658
CMD ["solargraph", "socket", "--host", "0.0.0.0", "--port", "7658"]
