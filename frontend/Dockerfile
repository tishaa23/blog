# Stage 1: Build
FROM node:latest AS build

WORKDIR /wanderlust/frontend

# Copy only package files first to leverage Docker layer caching
COPY package.json ./
COPY package-lock.json ./

RUN npm install

COPY . .

FROM node:alpine AS production


WORKDIR /wanderlust/frontend

COPY --from=build /wanderlust/frontend .

EXPOSE 5173

ENTRYPOINT ["npm", "run", "dev"]
