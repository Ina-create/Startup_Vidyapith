FROM node:18-alpine as build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Build the app
RUN npm run build

# Serve with Nginx
FROM nginx:alpine

# Copy custom nginx config
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy built files
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]