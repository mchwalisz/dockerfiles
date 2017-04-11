FROM ubuntu:latest
MAINTAINER Mikołaj Chwalisz <m.chwaliszATgmail.com>

RUN apt-get update && apt-get install -y \
    texlive-full biber latexmk make \
    graphviz default-jre \
    p7zip-full wget \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir /usr/share/plantuml
RUN wget -O /usr/share/plantuml/plantuml.jar http://sourceforge.net/projects/plantuml/files/plantuml.jar/download
RUN wget -O /usr/share/plantuml/batik-bin-1.9.tar.gz http://apache.mirror.digionline.de/xmlgraphics/batik/binaries/batik-bin-1.9.tar.gz
RUN tar -x -C /usr/share/plantuml -f /usr/share/plantuml/batik-bin-1.9.tar.gz
RUN wget -O /usr/share/plantuml/batik-bin-1.9.tar.gz http://apache.mirror.digionline.de/xmlgraphics/batik/binaries/batik-bin-1.9.tar.gz
RUN tar -x -C /usr/share/plantuml -f /usr/share/plantuml/batik-bin-1.9.tar.gz
RUN wget -O /usr/share/plantuml/fop-2.2-bin.tar.gz http://apache.mirror.digionline.de/xmlgraphics/fop/binaries/fop-2.2-bin.tar.gz
RUN tar -x -C /usr/share/plantuml -f /usr/share/plantuml/fop-2.2-bin.tar.gz

ADD plantuml /usr/bin/plantuml
ADD latexmkrc /root/.latexmkrc

WORKDIR /doc
VOLUME /doc
CMD ["latexmk"]
