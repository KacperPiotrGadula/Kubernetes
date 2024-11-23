# Select the base image for the build stage, based on Node.js 17.7.2 with the buster-slim variant
FROM node:17.7.2-buster-slim as build

# Set an ARG variable for the environment, defaulting to "production"
ARG NODE_ENV=production
# Assign the ARG variable value to the ENV environment variable
ENV NODE_ENV $NODE_ENV

# Set the working directory in the container for the build process
WORKDIR /code

# Copy the package files to the container to prepare for dependency installation
COPY package.json package-lock.json ./

# Install the required dependencies using npm
RUN npm install

# Copy the entire application source code to the container's working directory
COPY . /code
# Build the application using the npm build script
RUN npm run build

# Select the base image for the runtime stage, using nginx version 1.21.6
FROM nginx:1.21.6

# Copy the built application from the build stage to the nginx public HTML directory
COPY --from=build /code/build /usr/share/nginx/html

# Add a user with UID 5000 named "app" and create necessary directories for nginx
RUN useradd -u 5000 app \
    && mkdir -p /var/run/nginx /var/tmp/nginx \
    && chown -R app:app /usr/share/nginx /var/run/nginx /var/tmp/nginx

# Copy the custom nginx configuration files to their respective locations
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./default.conf /etc/nginx/conf.d/

# Set the working directory for runtime to nginx's public HTML directory
WORKDIR /usr/share/nginx/html
# Copy the environment configuration script and .env file to the working directory
COPY ./env.sh .env ./
# Make the environment configuration script executable
RUN chmod +x env.sh

# Switch to the "app" user for running the container processes
USER app:app

# Expose port 8080 for the application
EXPOSE 8080

# Run the environment script and start nginx in the foreground
CMD ["/bin/sh", "-c", "/usr/share/nginx/html/env.sh && nginx -g \"daemon off;\""]