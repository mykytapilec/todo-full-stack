# Stage 1: build backend
FROM node:22-slim AS builder

WORKDIR /app

COPY server/package*.json ./server/
COPY tsconfig.base.json ./
COPY shared ./shared
COPY server/tsconfig.json ./server/

WORKDIR /app/server
RUN npm install

COPY server ./server

RUN npm run build

# Stage 2: runtime
FROM node:22-slim AS runtime
WORKDIR /app

COPY server/package*.json ./server/
WORKDIR /app/server
RUN npm install --omit=dev

COPY --from=builder /app/server/dist ./dist
COPY --from=builder /app/shared ../shared

EXPOSE 8080
CMD ["node", "dist/src/index.js"]