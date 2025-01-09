# Docker file 
If you want to create an image from your own code, that you can push to dockerhub, you need to create a Dockerfile for your application.
A Dockerfile is a text document that contains all the commands a user could call on the command line to create an image.

# How to write a dockerfile 
1 Base image 
2 Bunch of commands that you run on the base image (to install dependencies like Node.js)


### Create file Docker 

- FROM node:16-alpine // base image 
- WORKDIR /app      // sets work dir of images as app 

- COPY . .        // copies files from our folder to image folder app 

- RUN npm install
- RUN npm run build        // these two build in app in image dir 
- RUN npx prisma generate        // generate prisma client 

EXPOSE 3000   // exposes port 3000 

CMD ["node" , "dist/index.js"]        // command to execute when starting container





### since we dont wantt to copt ndoe_moudles to docker WRKDIR/app as it gets intsall via RUN npm install 
- SO ignore we create   .dockerignore files and write node_modules into it 

### We can hardcorely send env variable to Docker file via ENV "envirnmoentcria" but it get exposes while pushing to github 
- So injext the environment varaible 

- docker run -p 3000:3000 -e DATABASE_URL="postgres://avnadmin:AVNS_EeDiMIdW-dNT4Ox9l1n@pg-35339ab4-harkirat-d1b9.a.aivencloud.com:25579/defaultdb?sslmode=require" image_name

### Building images with given tag name 
- docker build -t image_name 

Now we can see image in docker images

### Running the interactive shell inside the container 
docker exec -it <container_name_or_id> /bin/bash

-it means interactively (basically many commands)