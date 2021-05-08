FROM ghcr.io/ramoliyabiren/embedded_dockerbuilder/gccarm:dev

LABEL maintainer="ramoliya.biren@gmail.com"

# Define version
ENV NRFSDK_SERIES="15"
ENV NRFSDK_VERSION="0.0_a53641a"
ENV NRFCLI_SERIES="10"
ENV NRFCLI_VERSION_1="12"
ENV NRFCLI_VERSION_2="1"

# Install without user input
ENV DEBIAN_FRONTEND noninteractive

# Install NRF SDK
RUN wget --no-check-certificate -q https://developer.nordicsemi.com/nRF5_SDK/nRF5_SDK_v${NRFSDK_SERIES}.x.x/nRF5_SDK_${NRFSDK_SERIES}.${NRFSDK_VERSION}.zip
RUN mkdir /opt/nrf
RUN unzip -qq nRF5_SDK_${NRFSDK_SERIES}.${NRFSDK_VERSION}.zip -d /opt/nrf
RUN rm nRF5_SDK_${NRFSDK_SERIES}.${NRFSDK_VERSION}.zip
ENV NRF51_SDK_DIR=/opt/nrf/nRF5_SDK_${NRFSDK_SERIES}.${NRFSDK_VERSION}

# set Makefile.posix for SDK
RUN installed_arm_gcc_ver="$(arm-none-eabi-gcc -dumpversion)"
RUN echo "GNU_INSTALL_ROOT := /bin/"$'\r\n'"GNU_VERSION := $installed_arm_gcc_ver"$'\r\n'"GNU_PREFIX := arm-none-eabi"$'\r\n' > ${NRF51_SDK_DIR}/components/toolchain/gcc/Makefile.posix

#install nRFCommandLine Tools
RUN wget --no-check-certificate -q https://www.nordicsemi.com/-/media/Software-and-other-downloads/Desktop-software/nRF-command-line-tools/sw/Versions-${NRFCLI_SERIES}-x-x/${NRFCLI_SERIES}-${NRFCLI_VERSION_1}-${NRFCLI_VERSION_2}/nRFCommandLineTools${NRFCLI_SERIES}${NRFCLI_VERSION_1}${NRFCLI_VERSION_2}Linuxamd64.tar.gz
RUN mkdir nRFCommandLineTools
RUN tar xvf nRFCommandLineTools${NRFCLI_SERIES}${NRFCLI_VERSION_1}${NRFCLI_VERSION_2}Linuxamd64.tar.gz -C nRFCommandLineTools
RUN dpkg -i nRFCommandLineTools/nRF-Command-Line-Tools_${NRFCLI_SERIES}_${NRFCLI_VERSION_1}_${NRFCLI_VERSION_2}_Linux-amd64.deb
RUN rm -R nRFCommandLineTools
RUN rm nRFCommandLineTools${NRFCLI_SERIES}${NRFCLI_VERSION_1}${NRFCLI_VERSION_2}Linuxamd64.tar.gz
