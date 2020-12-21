ARG BUILD_FROM
FROM $BUILD_FROM

MAINTAINER David Ramos <info@davidramosweb.com>

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

# Download driver
ADD https://github.com/lwfinger/rtl8723bu/raw/master/rtl8723bu_nic.bin /lib/firmware/rtlwifi/rtl8723bu_nic.bin

# Install requirements for add-on
RUN apk update

COPY hostapd.conf /
COPY interfaces /etc/network/interfaces
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
