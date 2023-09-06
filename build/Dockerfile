FROM node:20-alpine@sha256:c843f4a4060246a25f62c80b3d4cf4a6b4c4639cdce421e4f2ee3102257225b4

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
