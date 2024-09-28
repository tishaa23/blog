# Stage 1: Build
FROM node:latest AS build

WORKDIR /wanderlust/backend

# Copy only package files first to leverage Docker layer caching
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the backend code
COPY . .

# Stage 2: Production
FROM node:alpine AS production

WORKDIR /wanderlust/backend

# Copy only the necessary files from the build stage
COPY --from=build /wanderlust/backend .

# Expose the application port
EXPOSE 5000

# Set the entry point
ENTRYPOINT ["npm", "start"]
