# Docker化が必要になった時用
FROM node:12 as node
COPY . /react-app
WORKDIR /react-app
RUN npm install && npm run build

FROM nginx:1.19.2-alpine
COPY --from=node ./react-app/build /usr/share/nginx/html
CMD nginx -g "daemon off;"
