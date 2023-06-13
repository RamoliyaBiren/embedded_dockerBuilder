FROM ghcr.io/ramoliyabiren/embedded_dockerbuilder/gccarm:dev

LABEL maintainer="ramoliya.biren@gmail.com"

# Install without user input
ENV DEBIAN_FRONTEND noninteractive

# Update
RUN apt-get clean
RUN apt-get update -qq
# Install PlatformIo
RUN python3 -c "$(curl -fsSL https://raw.githubusercontent.com/platformio/platformio/master/scripts/get-platformio.py)"
RUN pip install esptool
