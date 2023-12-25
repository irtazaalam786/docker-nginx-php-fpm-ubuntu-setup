# Use the official Nginx image as the base image
FROM nginx:latest

# Copy SSL certificates to the container
COPY ./my-site.local.crt /etc/ssl/certs/my-site.local.crt
COPY ./my-site.local.key /etc/ssl/private/my-site.local.key

RUN rm /etc/nginx/conf.d/default.conf

# Copy your custom Nginx configuration file to the container
COPY ./vhost /etc/nginx/conf.d/

