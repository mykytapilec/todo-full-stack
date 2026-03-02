# -------- Build stage --------
FROM node:22-slim AS builder
WORKDIR /app

COPY tsconfig.base.json ./
COPY shared ./shared

COPY client/package*.json ./client/

WORKDIR /app/client
RUN npm install

COPY client ./ 

RUN npm run build


# -------- Production stage --------
FROM nginx:alpine

COPY --from=builder /app/client/dist /usr/share/nginx/html
COPY client/nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80