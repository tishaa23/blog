
FROM node:latest

WORKDIR /wanderlust/backend

COPY package.json package-lock.json ./

RUN npm install

COPY . .

EXPOSE 5000

ENTRYPOINT ["npm", "start"]
