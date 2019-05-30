FROM debian:stretch-slim

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends -y apt-transport-https ca-certificates

COPY assets/snips.list /etc/apt/sources.list.d/
COPY assets/snips-debian.gpg /etc/apt/trusted.gpg.d/

ARG snipsver

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
        snips-satellite=$snipsver

ARG BUILD_DATE
ARG VCS_REF
LABEL org.opencontainers.image.created=$BUILD_DATE \
      org.opencontainers.image.authors="Thomas Liske <thomas@fiasko-nw.net>" \
      org.opencontainers.image.documentation="https://github.com/liske/snips-docker" \
      org.opencontainers.image.source="https://github.com/liske/snips-docker.git" \
      org.opencontainers.image.revision=$VCS_REF

USER _snips
ENTRYPOINT ["/usr/bin/snips-satellite"]
