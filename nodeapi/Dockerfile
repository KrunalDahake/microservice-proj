FROM node:14 as ui_image
WORKDIR /usr/src/app
COPY ./ ./api
RUN cd api && npm install

FROM node:14
WORKDIR /usr/src/app
COPY --from=ui_image /usr/src/app/api ./
CMD ["/bin/sh", "-c", "cd /usr/src/app && npm start"]
