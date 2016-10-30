FROM alpine:edge
MAINTAINER Mikołaj Chwalisz <m.chwaliszATgmail.com>

RUN echo 'http://dl-cdn.alpinelinux.org/alpine/edge/testing' >> /etc/apk/repositories

RUN apk update && \
    apk add texlive-full \
    texlive-xetex \
    biber \
    make \
    graphviz \
    openjdk8-jre \
    p7zip \
    wget

RUN mkdir /usr/share/plantuml
RUN wget -O /usr/share/plantuml/plantuml.jar http://sourceforge.net/projects/plantuml/files/plantuml.jar/download
RUN wget -O /usr/share/plantuml/batikAndFop.zip http://dl.dropbox.com/u/13064071/batikAndFop.zip
RUN 7z e -o/usr/share/plantuml /usr/share/plantuml/batikAndFop.zip

ADD plantuml /usr/bin/plantuml
ADD latexmkrc /root/.latexmkrc

WORKDIR /doc
VOLUME /doc
CMD ["latexmk"]
