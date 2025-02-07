# Use an official Nginx image
FROM nginx:alpine

# Copy Angular build to the Nginx directory
COPY dist/your-app-name /usr/share/nginx/html

# Copy custom Nginx configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
