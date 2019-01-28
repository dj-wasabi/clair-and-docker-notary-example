FROM alpine:3.8

ENV CLAIR_SCANNER_VERSION=v8

RUN apk --update --no-cache add curl && \
    curl -sSLo /bin/clair-scanner https://github.com/arminc/clair-scanner/releases/download/${CLAIR_SCANNER_VERSION}/clair-scanner_linux_amd64 && \
    chmod +x /bin/clair-scanner && \
    rm -rf /var/cache/apk/*

COPY entrypoint.sh /bin/entrypoint.sh

EXPOSE 9279

ENTRYPOINT ["/bin/entrypoint.sh"]
CMD []
