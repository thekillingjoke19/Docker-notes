**Docker Network** 
1) `docker network ls` checking the existing network in docker
2) `docker network create mongo-network` to create a manual network 
## start mongodb
```
docker run -d \
-p 27017:27017 \ 
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
--net mongo-network \
--name mongodb \
mongo
```
 

##  start mongo-express
```
docker run -d \
-p 8081:8081 \ 
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \ 
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \ 
-e ME_CONFIG_MONGIDB_SERVER=mongodb \ 
--net mongo-network \
--name mongo-express \
mongo-express
```

**Docker Compose**

```
version: '3'
services:
  mongodb:
    image: mongo
    ports:
     - 27017:27017
    environment:
     - MONGO_INITDB_ROOT_USERNAME=admin
     - MONGO_INITDB_ROOT_PASSWORD=password
  mongo-express:
    image: mongo-express
    ports:
     - 8080:8081
    environment:
      - ME_CONFIG_MONGODB_ADMINUSERNAME=admin
      - ME_CONFIG_MONGODB_ADMINPASSWORD=password
      - ME_CONFIG_MONGODB_SERVER=mongodb
```

 **what is Dockerfile**
1) Blueprint  for building images 
2) Dockerfile should always be called `Dockerfile` 
 3) `docker build -t my-app:1.0 .`  this command is use to build the image here `.` represents the location of docker file 
```
FROM node  // this creates node as the base of the image
ENV MONGO_DB_USERNAME=admin \
	MONGO_DB_PWD=password 
// optionally define env variables

RUN mkdir -p /home/app
 	// RUN = execute any linux , this directory is created instide the container
 
COPY . /home/app 
// this will be created outside container on the host
	 
CMD ["node","server.js"]	

```
**Image Naming in Docker registries**
 1)  registryDomain/imageName:tag
 