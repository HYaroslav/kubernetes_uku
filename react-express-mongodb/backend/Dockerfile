# syntax=docker/dockerfile:1.4

FROM node:lts-buster-slim AS development

# Create app directory
WORKDIR /usr/src/app_image

COPY package.json /usr/src/app_image/package.json
COPY package-lock.json /usr/src/app_image/package-lock.json
RUN npm ci

COPY . /usr/src/app_image

EXPOSE 3000

# install Docker tools (cli, buildx, compose)
COPY --from=gloursdocker/docker / /
WORKDIR /usr/src/app