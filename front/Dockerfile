FROM node:16-alpine as build-step
WORKDIR /app
COPY . /app
RUN npm install
RUN npm run build

FROM nginx
COPY --from=build-step /app/dist/tlcfront /usr/share/nginx/html

EXPOSE 80