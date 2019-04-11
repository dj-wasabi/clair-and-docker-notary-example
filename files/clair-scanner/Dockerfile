FROM alpine:3.8

ENV CLAIR_SCANNER_VERSION=v8

RUN apk --update --no-cache add curl ca-certificates && \
    curl -sSLo /bin/clair-scanner https://github.com/arminc/clair-scanner/releases/download/${CLAIR_SCANNER_VERSION}/clair-scanner_linux_amd64 && \
    chmod +x /bin/clair-scanner && \
    rm -rf /var/cache/apk/*

COPY ca-root.crt /usr/local/share/ca-certificates/ca-root.crt
COPY entrypoint.sh /bin/entrypoint.sh

RUN update-ca-certificates

EXPOSE 9279

ENTRYPOINT ["/bin/entrypoint.sh"]
CMD []
