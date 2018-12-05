FROM node:8.14.0-jessie

RUN (cd /opt && git clone https://github.com/volosincu/0x-starter-project.git)

WORKDIR /opt/0x-starter-project

RUN yarn install && yarn build
RUN yarn download_snapshot

EXPOSE 8577

COPY ./entrypoint.sh ./entrypoint.sh
ENTRYPOINT ["./entrypoint.sh"]
CMD []


