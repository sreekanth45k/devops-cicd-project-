# Use Nginx as base image
FROM nginx:latest

# Copy application files to Nginx default directory
COPY app /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]

