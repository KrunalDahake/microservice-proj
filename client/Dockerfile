FROM node:14 as web_image
WORKDIR /usr/src/app
COPY ./ ./client
RUN cd client && npm install && npm run build --prod

FROM nginx:latest
COPY --from=web_image /usr/src/app/client/dist/client  /usr/share/nginx/html
COPY ./nginx.conf /etc/nginx/conf.d/default.conf
