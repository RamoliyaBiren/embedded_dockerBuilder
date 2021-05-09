FROM ghcr.io/ramoliyabiren/embedded_dockerbuilder/gccarm:dev

LABEL maintainer="ramoliya.biren@gmail.com"

# Define version
LABEL NRFSDK_SERIES="15"
LABEL NRFSDK_VERSION="0.0_a53641a"
LABEL NRFCLI_SERIES="10"
LABEL NRFCLI_VERSION_1="12"
LABEL NRFCLI_VERSION_2="1"

# Install without user input
ENV DEBIAN_FRONTEND noninteractive

# Install NRF SDK
RUN wget --no-check-certificate -q https://developer.nordicsemi.com/nRF5_SDK/nRF5_SDK_v${NRFSDK_SERIES}.x.x/nRF5_SDK_${NRFSDK_SERIES}.${NRFSDK_VERSION}.zip
RUN mkdir /opt/nrf
RUN unzip -qq nRF5_SDK_${NRFSDK_SERIES}.${NRFSDK_VERSION}.zip -d /opt/nrf
RUN rm nRF5_SDK_${NRFSDK_SERIES}.${NRFSDK_VERSION}.zip
ENV NRF51_SDK_DIR=/opt/nrf/nRF5_SDK_${NRFSDK_SERIES}.${NRFSDK_VERSION}

# set Makefile.posix for SDK
RUN printf "GNU_INSTALL_ROOT := /bin/\r\nGNU_VERSION := $(arm-none-eabi-gcc -dumpversion)\r\nGNU_PREFIX := arm-none-eabi\r\n" > ${NRF51_SDK_DIR}/components/toolchain/gcc/Makefile.posix
RUN cat ${NRF51_SDK_DIR}/components/toolchain/gcc/Makefile.posix

#install nRFCommandLine Tools
RUN wget --no-check-certificate -q https://www.nordicsemi.com/-/media/Software-and-other-downloads/Desktop-software/nRF-command-line-tools/sw/Versions-${NRFCLI_SERIES}-x-x/${NRFCLI_SERIES}-${NRFCLI_VERSION_1}-${NRFCLI_VERSION_2}/nRFCommandLineTools${NRFCLI_SERIES}${NRFCLI_VERSION_1}${NRFCLI_VERSION_2}Linuxamd64.tar.gz
RUN mkdir nRFCommandLineTools
RUN tar xvf nRFCommandLineTools${NRFCLI_SERIES}${NRFCLI_VERSION_1}${NRFCLI_VERSION_2}Linuxamd64.tar.gz -C nRFCommandLineTools
RUN dpkg -i nRFCommandLineTools/nRF-Command-Line-Tools_${NRFCLI_SERIES}_${NRFCLI_VERSION_1}_${NRFCLI_VERSION_2}_Linux-amd64.deb
RUN rm -R nRFCommandLineTools
RUN rm nRFCommandLineTools${NRFCLI_SERIES}${NRFCLI_VERSION_1}${NRFCLI_VERSION_2}Linuxamd64.tar.gz
