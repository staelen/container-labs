FROM node:latest

## Docker Build

# Define environment variables
ENV APP_PORT=5000 APP_DIR=/fortune

# Create APP_DIR and cd to within
WORKDIR ${APP_DIR}

# Copy files from image to container
ADD main.js .
ADD package.json .
ADD public public
ADD views views

# Install dependencies
RUN npm install

## Docker Run

# Expose a port (doesn't actually expose a port, this is only for documentation purposes)
EXPOSE ${APP_PORT}
# Mount volume (doesn't actually mount a volume, this is only for documentation purposes)
VOLUME /fortune/node_modules

# Perform healthcheck on container
HEALTHCHECK --interval=60s --timeout=5s --start-period=5s --retries=3 CMD curl -f -s http://localhost:${APP_PORT}/health || exit 1

# Execute image
ENTRYPOINT [ "node", "main.js" ]