FROM node:18-alpine as installer

WORKDIR /app 

COPY package*.json ./

RUN yarn install 

COPY . .

RUN yarn run build

From nginx:latest as deployer
COPY --from=installer /app/build /usr/share/nginx/html


