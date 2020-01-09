FROM ubuntu:18.04
MAINTAINER Cleverson Nahum <cleversonahum@gmail.com>

VOLUME ["/dev/bus/usb"]

ENV USER=root
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt update && apt-get install linux-image-lowlatency linux-headers-lowlatency software-properties-common git wget git build-essential sudo psmisc vim -yq && GIT_SSL_NO_VERIFY=true git clone https://gitlab.eurecom.fr/oai/openairinterface5g.git 

WORKDIR /openairinterface5g/

RUN /bin/bash -c "source oaienv ; ./cmake_targets/build_oai -I  --eNB --install-system-files -w USRP;"