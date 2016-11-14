FROM alpine:3.4

ENV AURORA_VERSION 1.4

RUN apk add --update --no-cache tar curl && \
    curl -L https://github.com/Luxurioust/aurora/releases/download/$AURORA_VERSION/aurora_linux_amd64_v1.4.tar.gz | tar xvz -C /usr/local/bin && \
    chmod +x /usr/local/bin/aurora

EXPOSE 3000
ENTRYPOINT ["aurora"]
