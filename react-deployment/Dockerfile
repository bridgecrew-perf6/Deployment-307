FROM node:17 AS build

WORKDIR /app
COPY . /app
RUN npm install 
RUN npm run build

FROM nginx
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=build /app/build /usr/share/nginx/html
