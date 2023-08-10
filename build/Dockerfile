FROM node:20-alpine@sha256:d9d53500783a153234cc47d89a2f9117d1ed4eadf29cbeb46c377d172348aa73

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
