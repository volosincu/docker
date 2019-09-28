FROM node:12.10.0-alpine

RUN apk add --no-cache \
        bash \
    && apk add --no-cache --virtual .build-deps \
        curl \
  && curl -fsSLO --compressed https://github.com/elm/compiler/releases/download/0.19.0/binaries-for-linux.tar.gz \
  && mkdir /opt/elm \
  && tar -xzf binaries-for-linux.tar.gz -C /opt/elm \
  && ln -s /opt/elm/elm /usr/local/bin/elm \
  && apk del .build-deps

CMD ["bash"]