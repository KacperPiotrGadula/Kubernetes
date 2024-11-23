# Image with include nginx
FROM node:17.7.2-buster-slim

# Choose stage of apliaction
ARG NODE_ENV=production
ENV NODE_ENV $NODE_ENV

# Working dir
WORKDIR /app

# Choose aplikaction port
ARG PORT=8080
ENV PORT $PORT

# Add dependencies 
COPY package.json package-lock.json ./

# Instal ci in container
RUN npm ci

# Copy code apliation
COPY . /app

# Choose user which will use to run application inside container
USER node

CMD [ "node", "src/server.js" ]

