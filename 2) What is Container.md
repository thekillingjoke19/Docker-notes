1) a way to package app with all necessary dependencies and config
2) Portable artifact  , easily shared and moved around 
3) Makes dev more efficient 

Container Deepdive
1) They live in container repo
2) installation process different on each OS env.
3) Many steps where something could go wrong.
4) With Containers has own isolated env and just deploy/install container 
5) Will work regardless of the OS 
6) We can run different version of same app w/o conflct
7) W/O containers 
	1) Dev -> database (instruction to configuration) -> ops team will handle setting of env ->  can lead conflict -> Misunderstanding  b/w ops and devs 
8) W containers
	1) Package whole application in single unit/env just config that unit and deploy that<br>
9) What are containers (technically) -> these layers of images that are presented on top of Linux base (they are small in size)
10) Top of base image is application imageon top that is config data 
<h6>alpine is used docker coz small in size</h6>
11) Only different layers are downloaded 
12) docker ps -> running containers
13) Docker Image -> the actual built / artifcat that can be moved around 
14) Docker Container -> if the built is running and an env is created then it is a container . 
15) docker run postgres:10.10 (different layers are downloaded)

Difference Between Virtual Box and Docker
1) Working of Docker 
	 1) docker on top off Application on top off OS kernel on top off  hardware 
	 2) Uses kernel of its hosts
	 3) couple of mbs
	 4) Run much faster
	 5) Might not compatible with windows to work around docker toolbox
2) Working of VM
	1) VM run on top off and its own kernel  , doesnt
	2) use host kernel boots up its own
	3) couple of gigs
	4) Run slower in comparison
