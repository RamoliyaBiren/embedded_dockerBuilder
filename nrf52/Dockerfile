FROM ubuntu:20.04

LABEL maintainer="ramoliya.biren@gmail.com"

# Install without user input
ENV DEBIAN_FRONTEND noninteractive
# install ARM GCC toolchain & suporting Tools
RUN apt-get update -qq && apt-get install --no-install-recommends -y
RUN apt-get install -y gcc
RUN apt-get install -y git 
RUN apt-get install -y dos2unix 
RUN apt-get install -y apt-utils 
RUN apt-get install -y libyaml-dev 
RUN apt-get install -y gcc-arm-none-eabi 
RUN apt-get install -y libnewlib-arm-none-eabi 
RUN apt-get install -y binutils-arm-none-eabi 
RUN apt-get install -y build-essential 
RUN apt-get install -y make 
RUN apt-get install -y cppcheck 
RUN apt-get install -y doxygen 
RUN apt-get install -y graphviz 
RUN apt-get install -y unzip 
RUN apt-get install -y wget 

RUN wget -q https://developer.nordicsemi.com/nRF5_SDK/nRF5_SDK_v17.x.x/nRF5_SDK_17.0.2_d674dde.zip
RUN tar -xzf nRF5_SDK_17.0.2_d674dde.zip /opt/NRF
