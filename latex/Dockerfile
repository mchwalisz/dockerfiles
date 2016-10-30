FROM ubuntu:latest
MAINTAINER Mikołaj Chwalisz <m.chwaliszATgmail.com>

RUN apt-get update && apt-get install -y \
    texlive-full biber latexmk make \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /doc
VOLUME /doc
CMD ["latexmk"]
