FROM node:24

WORKDIR /app

COPY package*.json ./
COPY public ./public
COPY views ./views
COPY main.js ./

RUN npm install

EXPOSE 3000

ENV PORT=5000
ENV INSTANCE_NAME="name"
ENV INSTANCE_HASH="hash"

ENTRYPOINT ["node", "main.js"]