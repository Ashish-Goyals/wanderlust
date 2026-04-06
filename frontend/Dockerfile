FROM node:21 AS frontend-builder

WORKDIR /app
COPY package*.json ./
RUN npm i

COPY . .

FROM node:21-slim

WORKDIR /app

COPY --from=frontend-builder /app .

COPY .env.sample .env.local

EXPOSE 5173

CMD ["npm","run","dev", "--","--host"]







