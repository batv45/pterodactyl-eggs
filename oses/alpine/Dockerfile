
FROM        --platform=$TARGETOS/$TARGETARCH alpine:latest

LABEL       author="Batuhan OK" maintainer="activ45@hotmail.com" 

RUN         apk add --update --no-cache ca-certificates tzdata freeradius freeradius-mysql freeradius-eap openssl \
				&& adduser -D -h /home/container container
				

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container 

ADD --chown=root:container ./etc/raddb/ /etc/raddb

RUN /etc/raddb/certs/bootstrap && \
    chown -R root:container /etc/raddb/certs && \
    chmod 640 /etc/raddb/certs/*.pem

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]