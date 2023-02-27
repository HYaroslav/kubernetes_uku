# syntax=docker/dockerfile:1.4

# Create image based on the official Node image from dockerhub
FROM node:lts-buster AS development

# Create app directory
WORKDIR /usr/src/app_image

# Copy dependency definitions
COPY package.json /usr/src/app_image
COPY package-lock.json /usr/src/app_image

# Install dependecies
#RUN npm set progress=false \
#    && npm config set depth 0 \
#    && npm i install
RUN npm ci

# Get all the code needed to run the app
COPY . /usr/src/app_image

# Expose the port the app runs in
EXPOSE 3000

WORKDIR /usr/src/app

