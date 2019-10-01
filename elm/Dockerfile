FROM node:12.10.0-alpine

ENV ELM_VERSION 0.19.0

RUN apk add --no-cache bash \
    && apk add --no-cache --virtual .build-deps \
        curl \
  && curl -fsSLO --compressed "https://github.com/elm/compiler/releases/download/$ELM_VERSION/binaries-for-linux.tar.gz" \
  && mkdir /opt/elm \
  && tar -xzf binaries-for-linux.tar.gz -C /opt/elm \
  && ln -s /opt/elm/elm /usr/local/bin/elm \
  && rm -f binaries-for-linux.tar.gz \
  && apk del .build-deps

WORKDIR /wdir

RUN chmod 755 /wdir
USER node
CMD ["bash"]