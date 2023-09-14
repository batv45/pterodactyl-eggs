
FROM        --platform=$TARGETOS/$TARGETARCH alpine:3.13.1

LABEL       author="Batuhan OK" maintainer="activ45@hotmail.com" 

RUN         apk add --update --no-cache ca-certificates tzdata freeradius freeradius-mysql freeradius-eap openssl \
				&& adduser -D -h /home/container container
				 
RUN /home/container/raddb/certs/bootstrap && \
    chown -R root:radius /home/container/raddb/certs && \
    chmod 640 /home/container/raddb/certs/*.pem

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container  



COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]