Task-2  Containerize and running medusa application
Name: Pawan Bharat Mhaske
Date: 12-09-2024

Step-1: setting up the WSL in windows
Install and verify the nodejs

install and verify the git

install and verify the NPM

install and verify postgresql


install and verify docker and dockerd

installing the medusa and verifying the version of medusa
 
Test the docker and run a test container

After creating the medusa application and make the dockerfile and dockerfile 


Docker-compose file
version: '3'
services:
  db:
    image: postgres
    volumes:
      - postgres-db:/var/lib/postgresql/data
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=pawan@123
    ports:
     - "5432:5432"
volumes:
  postgres-db:

in this file we are mounting the volume ‘postgres-db’ to the ‘/var/lib./postgresql/data’ directory for persistent backup












Step-2: building up the docker-compose.yml

Building up and configuring the volume using ‘docker exec’ command



Checking the directory that we mounted on the postgres-db volume you can check the container volume path using.
-	cd /var/lib/docker/volumes/
-	ls



step-3: building an image from dockerfile and running a container from it
Dockerfile

FROM node:18-alpine AS build
# Set working directory
WORKDIR /app
# Copy package.json and package-lock.json
COPY package*.json ./
# Install dependencies
RUN npm install --legacy-peer-deps
# Copy the rest of the application
COPY . .

# Stage 2: Run the application
FROM node:18-alpine
# Set working directory
WORKDIR /app
# Install Medusa CLI globally again
RUN npm install -g @medusajs/medusa-cli
# Copy the built application from the build stage
COPY --from=build /app .

# Expose the port the app runs on
EXPOSE 7001

# Run migrations and then start the application
CMD ["sh", "-c", "medusa migrations run && npm run start"]
 


 
Building an image from the dockerfile and verifying it


Running a container from it

docker run --name medusa \
  -v postgres-db:/var/lib/postgresql/data \
  -p 7001:7001 \
  -e POSTGRES_DB=postgres \
  -e POSTGRES_USER=postgres \
  -e POSTGRES_PASSWORD=pawan@123 \
  web-app


Or
npx create-medusa-app@latest –-seed –db-url postgres://postgres:<password>@localhost:5432/postgres 
 

accessing it using http://localhost:7001
login with correct credentials.


 





