FROM debian

RUN apt-get update
RUN apt-get -y install texlive-full latexmk ghostscript fonts-noto-cjk make perl

WORKDIR /src

CMD ["latexmk", "-pdfdvi"]