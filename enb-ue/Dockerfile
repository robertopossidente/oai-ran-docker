FROM base-ran
MAINTAINER Lucas Novoa <lucasnmartins300@gmail.com>

VOLUME ["/dev/bus/usb"]
VOLUME ["/config_files"]

ENV USER=root
ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /
RUN /bin/bash -c "cp -r openairinterface5g enb; cp -r openairinterface5g ue;"

WORKDIR /enb
RUN /bin/bash -c "sed -i '102i\ host=NULL;\' ./openair3/NAS/UE/API/USER/user_api.c "
RUN /bin/bash -c "source oaienv; ./cmake_targets/build_oai -w USRP --eNB"

WORKDIR /ue
RUN /bin/bash -c "sed -i '102i\ host=NULL;\' ./openair3/NAS/UE/API/USER/user_api.c "
RUN /bin/bash -c "source oaienv; ./cmake_targets/build_oai --UE"

