FROM node:18-alpine AS build

RUN set -xe; \
	mkdir -p /usr/src/app; \
	mkdir -p /app-clone; \
	apk update; \
	apk add git; \
	git clone "https://github.com/owenashurst/agar.io-clone.git" /app-clone

WORKDIR /usr/src/app

RUN set -xe; \
	cp /app-clone/package.json /usr/src/app/package.json; \
	npm install; \
	npm cache clean --force; \
	cp -r /app-clone/. /usr/src/app; \
	rm -rf /app-clone; \
	npm run build

