# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
# Use the node:6-alpine image as the base image
FROM node:6-alpine

# Set the working directory for the application
WORKDIR /usr/src/app

# Install the tini package using the Alpine package manager
RUN apk add --no-cache tini

# Copy the package.json file to the working directory
COPY package.json .

# Install the dependencies and clean the npm cache
RUN npm install && npm cache clean --force

# Copy all files from the current directory to the working directory
COPY . .

# Expose port 80 of the Docker host
EXPOSE 80

# Define the command to start the container
CMD ["/sbin/tini", "--", "node", "./bin/www"]


# Remaining commands
# 1- Build the Dockerfile
# Replace "your-dockerhub-account/repository-name" with your actual Docker Hub repository name
# docker build -t your-dockerhub-account/repository-name .

# 2- Start a container locally to ensure it works on http://localhost
# docker run -p 80:80 your-dockerhub-account/repository-name

# 3- Ensure the image is named properly for your Docker Hub account with a new repository name
# docker tag your-dockerhub-account/repository-name your-dockerhub-account/new-repository-name

# 4- Push the image to Docker Hub
# docker push your-dockerhub-account/new-repository-name

# Go to https://hub.docker.com to verify that you pushed the image correctly

# 5- Remove the local image from cache
# docker image rm your-dockerhub-account/repository-name

# 6- Start a new container from your Hub image, and watch how it auto downloads and runs
# docker run -p 80:80 your-dockerhub-account/new-repository-name

# Test again that it works at http://localhost
