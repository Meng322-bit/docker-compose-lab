FROM node:24-slim

WORKDIR /app

COPY package*.json ./

RUN apt-get update && apt-get install -y python3 make g++ \
    && npm install --omit=dev \
    && apt-get purge -y python3 make g++ \
    && apt-get autoremove -y \
    && rm -rf /var/lib/apt/lists/*

COPY . .

EXPOSE 3002

CMD ["node", "index.js"]