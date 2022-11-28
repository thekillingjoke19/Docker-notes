1) Port binded to the container is 5000
2) `docker pull` this pulls the images 
3) `docker images ` checks the images that are present on the laptop
4) `docker run image_name` runs the existing image 
5)  `docker ps` list down the running containers
6) `docker run -d redis` this will run the container in the detached mode and we will get docker id (hash) as the output 
7) `docker stop id (docker ps id of that container)` this will stop the container . To rerun the container we can just `docker run id(docker ps id of that container)` . 
8) `docker ps -a` this will list all the container which are either running or not running
9) `docker run redis:version` this will pull the image and starts to run it  
10) `docker run -p6000:6379 redis` this will bind the port of the container 6379 to out localhost that is 6000 .
11) `docker rm container_name` remove the container

**Debugging Docker** 
1)  `docker logs container_id` . 
2) `docker run -d port_host:port_container --name docker-older docker_image:version` this is used to rename the container 
3) `docker exec -it id(docker ps id)  /bin/bash` opens the terminal of the particular docker file   

