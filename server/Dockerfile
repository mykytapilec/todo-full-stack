# ---------- Stage 1: build ----------
FROM node:22-slim AS builder

WORKDIR /app

COPY tsconfig.base.json ./
COPY shared ./shared

COPY server ./server

WORKDIR /app/server

RUN npm install
RUN npm run build


# ---------- Stage 2: runtime ----------
FROM node:22-slim

WORKDIR /app

COPY tsconfig.base.json ./
COPY shared ./shared
COPY server/package*.json ./server/

WORKDIR /app/server
RUN npm install --omit=dev

COPY --from=builder /app/server/dist ./dist

EXPOSE 8080

CMD ["node", "dist/server/src/index.js"]