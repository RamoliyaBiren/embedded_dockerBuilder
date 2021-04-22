FROM ubuntu:20.04

LABEL maintainer="ramoliya.biren@gmail.com"

# install ARM GCC toolchain & suporting Tools
RUN apt-get update -qq && apt-get install --no-install-recommends -y
RUN apt-get update gcc -y
RUN apt-get update git -y
RUN apt-get update dos2unix -y
RUN apt-get update apt-utils -y
RUN apt-get update libyaml-dev -y
RUN apt-get update gcc-arm-none-eabi -y
RUN apt-get update libnewlib-arm-none-eabi -y
RUN apt-get update binutils-arm-none-eabi -y
RUN apt-get update build-essential -y
RUN apt-get update make -y
RUN apt-get update cppcheck -y
RUN apt-get update doxygen -y
RUN apt-get update graphviz -y
RUN apt-get update unzip -y
RUN apt-get update wget -y

RUN wget -q https://developer.nordicsemi.com/nRF5_SDK/nRF5_SDK_v17.x.x/nRF5_SDK_17.0.2_d674dde.zip
RUN tar -xzf nRF5_SDK_17.0.2_d674dde.zip /opt/NRF
