FROM ubuntu:16.04
MAINTAINER Cleverson Nahum <cleversonahum@gmail.com>

VOLUME ["/dev/bus/usb"]
VOLUME ["/config_files"]

ENV USER=root
ENV DEBIAN_FRONTEND=noninteractive


RUN apt-get update && apt-get -y install git && apt-get -y install vim && git clone https://lasseufpa:lasse123@gitlab.eurecom.fr/flexran/flexran.git

WORKDIR ./flexran

RUN git submodule init && sed -i 's/https:\/\/gitlab.eurecom.fr\/flexran\/flexran-rtc.git/https:\/\/lasseufpa:lasse123\@gitlab.eurecom.fr\/flexran\/flexran-rtc.git/' .git/config && git config credential.helper store && git submodule update --remote controller && apt-get update && apt-get -y install gawk && apt-get -y install sudo && sudo apt-get -y install git libprotobuf-dev protobuf-compiler lsb-release build-essential g++ python-dev autotools-dev libicu-dev libbz2-dev libboost-all-dev default-jre default-jre-headless curl wget vim

WORKDIR ./controller

RUN git checkout v2.2 && sudo curl -sL https://deb.nodesource.com/setup_14.x | bash && sudo apt -y install nodejs && sudo npm install -g apidoc && npm install -g npm && npm install -g n && n stable && apidoc -i src/ -o ./docs -f ".*\\.cc$" -f ".*\\.h$" && ./tools/install_dependencies && ./build_flexran_rtc.sh 


