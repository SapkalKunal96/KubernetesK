FROM node:18-alpine AS Installer

WORKDIR /app

COPY . /app

RUN npm install

RUN npm run build

FROM nginx:latest AS Deployer

COPY --from=Installer /app/build /usr/share/nginx/html
 
