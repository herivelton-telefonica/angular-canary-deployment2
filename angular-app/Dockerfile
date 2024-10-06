FROM node:20 AS build-stage
WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build --prod

FROM nginx:alpine
COPY --from=build-stage /app/dist/angular-app/browser /usr/share/nginx/html