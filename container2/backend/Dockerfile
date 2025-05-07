# Use official Node.js 18 image
FROM node:18-alpine

# Set working directory
WORKDIR /usr/src/app

# Copy package files first for better caching
COPY package*.json ./

# Install production dependencies only
RUN npm install --only=production

# Copy all other files
COPY . .

# Use port 8080 (required by Cloud Run)
ENV PORT=8080
EXPOSE 8080

# Start the application
CMD ["node", "server.js"]