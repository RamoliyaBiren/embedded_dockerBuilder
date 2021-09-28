FROM ghcr.io/ramoliyabiren/embedded_dockerbuilder/gccarm:dev

LABEL maintainer="ramoliya.biren@gmail.com"

# Install without user input
ENV DEBIAN_FRONTEND noninteractive
ENV LICENSE_ALREADY_ACCEPTED 1

# Update
RUN apt-get clean
RUN apt-get update -qq
# Install STCubeIDE
RUN wget --no-check-certificate -q https://www.st.com/content/ccc/resource/technical/software/sw_development_suite/group0/03/90/a4/d6/7c/f2/40/b0/stm32cubeide_deb/files/st-stm32cubeide_1.7.0_10852_20210715_0634_amd64.deb_bundle.sh.zip/jcr:content/translations/en.st-stm32cubeide_1.7.0_10852_20210715_0634_amd64.deb_bundle.sh.zip
RUN mkdir /opt/st
RUN unzip -qq en.st-stm32cubeide_1.7.0_10852_20210715_0634_amd64.deb_bundle.sh.zip -d /opt/st
RUN rm en.st-stm32cubeide_1.7.0_10852_20210715_0634_amd64.deb_bundle.sh.zip
RUN y | sh ./opt/st/st-stm32cubeide_1.7.0_10852_20210715_0634_amd64.deb_bundle.sh
RUN rm /opt/st/st-stm32cubeide_1.7.0_10852_20210715_0634_amd64.deb_bundle.sh
RUN ln -sf /opt/st/stm32cubeide_1.7.0/stm32cubeide /bin/
