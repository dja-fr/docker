#Usage Example : docker run -v /tmp/.X11-unix:/tmp/.X11-unix -v /datas/roms/:/datas/roms -e DISPLAY=unix$DISPLAY --device /dev/snd --name dgen dgen /datas/roms/SOR.SMD

FROM ubuntu:16.04


RUN apt-get update && apt-get install -y  libsdl-sound1.2-dev libsdl-image1.2-dev  libsdl-gfx1.2-dev  libsdl-console-dev libsdl1.2-dev libsdl-image1.2-dev

#GET the 1.33 version of dgen

ADD https://sourceforge.net/projects/dgen/files/dgen/1.33/dgen-sdl-1.33.tar.gz/download /tmp/dgen-sdl-1.33.tar.gz

RUN  cd /tmp && tar -zxvf dgen-sdl-1.33.tar.gz

#Compile and install 
RUN cd /tmp/dgen-sdl-1.33 && ./configure && make && make install

RUN mkdir -p /datas/roms

ENTRYPOINT ["dgen"]


LABEL version="0.1"
LABEL description="Docker image that contains dgen emulator for Sega Megadrive."
LABEL maintainer="dja-fr"

