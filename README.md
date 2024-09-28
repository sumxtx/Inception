# Inception

_This project consists in set up a small infrastructure
composed of different services under specific rules.  
The whole project has to be done in a virtual machine._

## Rules 

* You have to use docker compose.  
* Write your own Dockerfiles, one per service.  
* The Dockerfiles must be called in your docker-compose.yml by your Makefile.  
* The containers must be built either from the penultimate stable version of __Alpine__ or __Debian__.  
* Each Docker image must have the same name as its corresponding service.  
* Each service has to run in a dedicated container.  

• A Docker container that contains NGINX with TLSv1.2 or TLSv1.3 only.  
• A Docker container that contains WordPress + php-fpm (it must be installed and configured) only.  
• A Docker container that contains MariaDB only.  
• A volume that contains your WordPress database.  
• A second volume that contains your WordPress website files.  
• A docker-network that establishes the connection between your containers.  


> __You have to build yourself the Docker images of your project.  
It is then forbidden to pull ready-made Docker images.  
As well as using services such as DockerHub  
(Alpine/Debian being excluded from this rule).__  

- - - - 
Here is an example diagram of the expected result:  
<p> 
<img src="https://github.com/sumxtx/Inception/blob/main/assets/2024-09-28_19-34.png" width="100%" height="50%" position="center">
</p>


