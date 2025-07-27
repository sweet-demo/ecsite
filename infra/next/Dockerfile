FROM node:18-alpine

WORKDIR /app

COPY fe/package*.json ./

RUN npm install

COPY fe .

EXPOSE 3000

CMD ["npx", "next", "dev", "--turbopack"] 