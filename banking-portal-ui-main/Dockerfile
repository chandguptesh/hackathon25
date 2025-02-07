FROM node:18 AS build

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install --legacy-peer-deps

# Copy source code
COPY . .

# Build the Angular app
RUN npm run build --prod

# Use Nginx for serving the Angular app
FROM nginx:alpine

# Copy built app to Nginx directory
COPY --from=build /app/dist /usr/share/nginx/html

# Copy custom Nginx configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port
EXPOSE 8080

# Run Nginx
CMD ["nginx", "-g", "daemon off;"]
