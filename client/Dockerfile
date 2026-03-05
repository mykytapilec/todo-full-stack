# ===== Stage 1: Build frontend =====
FROM node:22-slim AS builder

WORKDIR /app

COPY tsconfig.base.json ./
COPY shared ./shared

WORKDIR /app/client

COPY client/package*.json ./
COPY client/tsconfig.json ./

RUN npm install

COPY client/src ./src
COPY client/index.html ./
COPY client/vite.config.ts ./
COPY client/*.ts ./
COPY client/*.tsx ./

RUN npm run build


# ===== Stage 2: Nginx =====
FROM nginx:alpine AS runtime

COPY --from=builder /app/client/dist /usr/share/nginx/html
COPY client/nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]