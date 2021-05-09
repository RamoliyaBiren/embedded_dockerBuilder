FROM ubuntu:20.04

LABEL maintainer="ramoliya.biren@gmail.com"

# Install without user input
ENV DEBIAN_FRONTEND noninteractive

# install ARM GCC tool-chain & supporting Tools
RUN apt-get update -qq && apt-get install --no-install-recommends -y \
gcc \
git \
dos2unix \
apt-utils \
libyaml-dev \ 
gcc-arm-none-eabi  \
libnewlib-arm-none-eabi \
binutils-arm-none-eabi \
build-essential \
make \
cppcheck \
doxygen \
graphviz \
unzip \
wget 

