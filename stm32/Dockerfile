FROM ghcr.io/ramoliyabiren/embedded_dockerbuilder/gccarm:dev

LABEL maintainer="ramoliya.biren@gmail.com"

# Install without user input
ENV DEBIAN_FRONTEND noninteractive
ENV LICENSE_ALREADY_ACCEPTED 1

# Update
RUN apt-get clean
RUN apt-get update -qq
RUN pip install esptool
# Install STCubeIDE
RUN wget --no-check-certificate -q https://www.st.com/content/ccc/resource/technical/software/sw_development_suite/group0/30/a8/7a/1c/24/19/42/c0/stm32cubeide-lnx/files/st-stm32cubeide_1.12.1_16088_20230420_1057_amd64.sh.zip/jcr:content/translations/en.st-stm32cubeide_1.12.1_16088_20230420_1057_amd64.sh.zip
RUN mkdir /opt/st
RUN unzip -qq en.st-stm32cubeide_1.12.1_16088_20230420_1057_amd64.sh.zip -d /opt/st
RUN rm en.st-stm32cubeide_1.12.1_16088_20230420_1057_amd64.sh.zip
RUN y | sh ./opt/st/st-stm32cubeide_1.12.1_16088_20230420_1057_amd64.deb_bundle.sh
RUN rm /opt/st/st-stm32cubeide_1.12.1_16088_20230420_1057_amd64.deb_bundle.sh
RUN ln -sf /opt/st/stm32cubeide_1.12.0/stm32cubeide /bin/
