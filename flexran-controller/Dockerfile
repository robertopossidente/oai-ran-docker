FROM ubuntu:18.04
MAINTAINER Cleverson Nahum <cleversonahum@gmail.com>

ENV USER=root
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt install -yq git && git clone https://gitlab.eurecom.fr/flexran/flexran.git

WORKDIR /flexran/

RUN git submodule init && git submodule update --remote controller