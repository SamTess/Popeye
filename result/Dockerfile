FROM node:20-alpine AS builder

WORKDIR /app

COPY . .

RUN rm -rf node_modules
RUN npm install

FROM node:20-alpine

WORKDIR /app

COPY --from=builder /app .

EXPOSE 80

CMD ["node", "server.js"]