# Base image ( apline - small version of image without add. deps )
FROM node:lts-alpine

# Create this dir to not copy all local files into root dir of container to not conflict with base image folder / file names
WORKDIR /usr/app

# Copy package.json to the files of base image 
# ( <path to the folder to copy on your mashine (relative to build context (docker build -> simple web) )> / place to copy stuff to inside the container ) 
# if I did not change the folder ( cd ../ ) I will in WORKDIR /usr/app
COPY ./ ./

# Install dependencies
RUN npm install

# Set port for container to reach ( to make requests from local mashine to be listened by container, map port of app to port of contaner )
# redirect request comes in to 8080 in local mashine to port 8080 inside the container 8080 ( can be different )
# request from browser -p 5000:8080 map to 8080 inside the container
# EXPOSE 3000 should be like in node app/index
EXPOSE 3000

# Default command
CMD ["npm", "start"]
