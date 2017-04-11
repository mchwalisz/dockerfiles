Useful dockerfiles
==================

- [latex](https://hub.docker.com/r/mchwalisz/latex/): Build latex projects in docker environment

    - Build: `docker build . -t mchwalisz/latex`
    - Run: `docker run -t mchwalisz/latex -v $(pwd):/doc`
    - Run: `docker run -t mchwalisz/latex -v $(pwd):/doc latexmk -f`
