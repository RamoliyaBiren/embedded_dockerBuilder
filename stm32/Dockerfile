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
RUN wget --no-check-certificate -q "https://onedrive.live.com/download?cid=8A816C95CF340AE6&resid=8A816C95CF340AE6%21333&authkey=AMUoB9lYiA50SDY" -O stm32cubeide.zip
RUN mkdir /opt/st
RUN unzip -qq stm32cubeide.zip -d /opt/st
RUN rm stm32cubeide.zip
RUN y | sh ./opt/st/st-stm32cubeide_1.12.1_16088_20230420_1057_amd64.deb_bundle.sh
RUN rm /opt/st/st-stm32cubeide_1.12.1_16088_20230420_1057_amd64.deb_bundle.sh
RUN ln -sf /opt/st/stm32cubeide_1.12.1/stm32cubeide /bin/
