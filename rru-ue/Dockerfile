FROM base-ran
MAINTAINER Lucas Nóvoa <lucasnmartin300@gmail.com>

VOLUME ["/dev/bus/usb"]
VOLUME ["/config_files"]

ENV USER=root
ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /openairinterface5g/

RUN /bin/bash -c "source oaienv; sudo apt-get install net-tools && apt-get install iputils-ping && apt-get update; ./cmake_targets/build_oai --UE"
