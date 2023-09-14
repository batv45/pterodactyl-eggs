
FROM        --platform=$TARGETOS/$TARGETARCH alpine:3.13.1

LABEL       author="Batuhan OK" maintainer="activ45@hotmail.com" 

RUN         apk add --update --no-cache ca-certificates tzdata freeradius freeradius-mysql freeradius-eap openssl \
				&& adduser -D -h /home/container container
				

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container 
 

RUN /etc/raddb/certs/bootstrap && \
    chown -R root:container /etc/raddb/certs && \
    chmod 640 /etc/raddb/certs/*.pem

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]