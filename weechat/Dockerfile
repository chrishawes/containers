FROM alpine:edge

RUN apk --update --no-cache add weechat ruby py2-pip python python-dev build-base py-dbus && \
    pip install --upgrade pip && \
    pip install python-potr && \
    pip install notify2 && \
    apk del python-dev py2-pip build-base

RUN addgroup -S weechat && adduser weechat -D -S -s /sbin/nologin -G weechat weechat && \
    weechat --version

USER weechat

ENTRYPOINT ["weechat"]
