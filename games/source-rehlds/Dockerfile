FROM ghcr.io/pterodactyl/games:source

LABEL author="Batuhan OK" maintainer="activ45@hotmail.com"
LABEL org.opencontainers.image.description="cs16 ReHlds"

RUN apt install -y curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc-s1 lib32stdc++6 libsdl2-2.0-0:i386 steamcmd

COPY ./files /home/container