FROM node:18-alpine

WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the code
COPY . .

# Expose the port your backend uses (5000)
EXPOSE 5000

# Start the server
CMD ["node", "-r", "crypto", "server.js"]