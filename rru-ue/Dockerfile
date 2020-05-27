FROM base-ran
MAINTAINER Cleverson Nahum <cleversonahum@gmail.com>

VOLUME ["/dev/bus/usb"]
VOLUME ["/config_files"]

ENV USER=root
ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /openairinterface5g/

RUN /bin/bash -c "git checkout -f v1.0.0; source oaienv; sudo apt-get install net-tools && apt-get install iputils-ping && apt-get update; ./cmake_targets/build_oai -I --UE -t ETHERNET --musim"
