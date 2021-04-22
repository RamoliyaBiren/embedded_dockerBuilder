FROM ubuntu:20.04

LABEL maintainer="ramoliya.biren@gmail.com"

# install ARM GCC toolchain & suporting Tools
RUN apt-get update -qq && apt-get install --no-install-recommends -y
RUN apt-get install gcc -y
RUN apt-get install git -y
RUN apt-get install dos2unix -y
RUN apt-get install apt-utils -y
RUN apt-get install libyaml-dev -y
RUN apt-get install gcc-arm-none-eabi -y
RUN apt-get install libnewlib-arm-none-eabi -y
RUN apt-get install binutils-arm-none-eabi -y
RUN apt-get install build-essential -y
RUN apt-get install make -y
RUN apt-get install cppcheck -y
RUN apt-get install doxygen -y
RUN apt-get install graphviz -y
RUN apt-get install unzip -y
RUN apt-get install wget -y

RUN wget -q https://developer.nordicsemi.com/nRF5_SDK/nRF5_SDK_v17.x.x/nRF5_SDK_17.0.2_d674dde.zip
RUN tar -xzf nRF5_SDK_17.0.2_d674dde.zip /opt/NRF
