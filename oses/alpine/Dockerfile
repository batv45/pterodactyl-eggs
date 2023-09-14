
FROM        --platform=$TARGETOS/$TARGETARCH alpine:latest

LABEL       author="Batuhan OK" maintainer="activ45@hotmail.com" 

RUN         apk add --update --no-cache ca-certificates tzdata freeradius freeradius-mysql freeradius-eap openssl \
				&& adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container 

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]