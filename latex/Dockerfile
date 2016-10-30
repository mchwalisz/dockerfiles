FROM ubuntu:latest
MAINTAINER Mikołaj Chwalisz <m.chwaliszATgmail.com>

RUN apt-get update && apt-get install -y \
    texlive-full biber latexmk make \
    graphviz default-jre \
    p7zip-full wget \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir /usr/share/plantuml
RUN wget -O /usr/share/plantuml/plantuml.jar http://sourceforge.net/projects/plantuml/files/plantuml.jar/download
RUN wget -O /usr/share/plantuml/batikAndFop.zip http://dl.dropbox.com/u/13064071/batikAndFop.zip
RUN 7z e -o/usr/share/plantuml /usr/share/plantuml/batikAndFop.zip

ADD plantuml /usr/bin/plantuml
ADD latexmkrc /root/.latexmkrc

WORKDIR /doc
VOLUME /doc
CMD ["latexmk"]
