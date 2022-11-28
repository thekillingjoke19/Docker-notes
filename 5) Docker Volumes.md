1) When do we need Docker Volumes
2) What is Docker Volumes
3) 3 Volumes Types
4) Docker Volumes in docker-compose file

<p>The need for the volumes arise when the data stored inside the container is gone when the container is restarted or shut down . So to solve that we used docker volumes where the data is stored on the physical device and mounted to the container file system path . So when the data is edited or changed in the container file system the changes are automatically applied on the host </p>


3 Volume Types
1) Via docker run . `docker run -v host_from_mounted:container_to_be_mounted_on` 
2) Anonymous volumes -> where we create volume just by referencing the directory . We do not specify which directory on the host to be mounted but that is taken care by docker itself  . Automatically created on the host in docker in `/var/lib/docker/volumes/random-hash/_data ` 
3) Named Volumes  . It need only the name in the folder on the host machine . We can reference the volumes using names . Should be used only in production  . 