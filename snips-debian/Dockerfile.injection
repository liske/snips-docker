ARG snipsver
ARG imgbase=snips-platform:$snipsver

FROM $imgbase

ARG BUILD_DATE
ARG VCS_REF
LABEL org.opencontainers.image.created=$BUILD_DATE \
      org.opencontainers.image.authors="Thomas Liske <thomas@fiasko-nw.net>" \
      org.opencontainers.image.documentation="https://github.com/liske/snips-docker" \
      org.opencontainers.image.source="https://github.com/liske/snips-docker.git" \
      org.opencontainers.image.revision=$VCS_REF

USER _snips
ENTRYPOINT ["/usr/bin/snips-injection"]
