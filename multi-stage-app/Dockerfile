FROM node:18-alpine AS installer

WORKDIR /app 

COPY package*.json ./

RUN yarn install 

COPY . .

#RUN yarn run build

FROM nginx:latest AS deployer
COPY --from=installer /app/src /usr/share/nginx/html


