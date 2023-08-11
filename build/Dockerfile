FROM node:20-alpine@sha256:80f3be1363191811dd25cc8cb966241a30555d95a082b69487435c9e09236bb7

ARG UID=1000
ARG GID=1000

RUN apk add -U clang lld wasi-sdk
RUN mkdir /home/node/undici

WORKDIR /home/node/undici

COPY package.json .
COPY build build
COPY deps deps
COPY lib lib

RUN npm i

USER node
