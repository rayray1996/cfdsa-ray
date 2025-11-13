FROM node:24 AS builder

WORKDIR /src

COPY package.json package-lock.json ./
RUN npm install -g @angular/cli

COPY *.json .
COPY public public
COPY src src

RUN npm ci && ng build

FROM caddy:latest

WORKDIR /app

COPY caddy/Caddyfile .

RUN mkdir html
COPY caddy/error.html html

COPY --from=builder /src/dist/angular/browser/ html

ENV CADDY_PORT=3000

EXPOSE ${CADDY_PORT}

CMD ["caddy", "run", "--config", "/app/Caddyfile"]