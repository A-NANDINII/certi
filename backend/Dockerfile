# Backend Dockerfile
FROM node:18

# Create app directory
WORKDIR /usr/src/app

# Copy and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the backend files
COPY . .

# Expose port and run
EXPOSE 5000
CMD ["node", "index.js"]
