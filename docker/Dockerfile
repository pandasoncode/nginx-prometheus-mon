FROM node:14.21.3-alpine3.17 as build
WORKDIR /app
COPY ./ /app/
RUN npm install
RUN npm run build --prod

FROM nginx:alpine 
COPY --from=build /app/dist/angular-hello-world /usr/share/nginx/html
COPY ./nginx-custom.conf /etc/nginx/conf.d/default.conf
