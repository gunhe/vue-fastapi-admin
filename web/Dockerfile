# FROM node:20-alpine AS web
# FROM node:22-slim as web
FROM docker.1ms.run/node:22-slim as web
WORKDIR /opt/vue-fastapi-admin
COPY . .
RUN npm i --registry=https://registry.npmmirror.com && npm run build


FROM openresty/openresty:alpine as prod
# FROM docker.1ms.run/openresty/openresty:alpine

ENV TZ=Asia/Shanghai

COPY --from=web /opt/vue-fastapi-admin/dist /usr/local/openresty/nginx/html
COPY nginx.conf /usr/local/openresty/nginx/conf/nginx.conf

EXPOSE 80
