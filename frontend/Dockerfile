# Stage 1: Build React app
FROM node:18 AS build

WORKDIR /app

COPY package*.json ./

# Ensure permissions and install dependencies
RUN npm install

COPY . .

# Fix: Ensure react-scripts has execute permission
RUN chmod +x node_modules/.bin/react-scripts

# Build the app
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:stable-alpine

COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
