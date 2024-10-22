FROM node:18-alpine AS installer

WORKDIR /app 

COPY package*.json ./

RUN yarn install 

COPY . .

RUN yarn run build

FROM python3 AS deployer
COPY --from=installer /app/build /usr/share/nginx/html


