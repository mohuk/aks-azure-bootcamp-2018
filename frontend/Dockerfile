FROM node:8.9.4-alpine as node

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm install

COPY ./ /app/

RUN npm run build


FROM nginx:1.11.12-alpine

COPY --from=node /app/dist/ /usr/share/nginx/html

COPY ./nginx.conf /etc/nginx/conf.d/default.conf
