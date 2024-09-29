# Inception
- - - -
_This project consists in set up a small infrastructure
composed of different services under specific rules.  
The whole project has to be done in a virtual machine._


## Rules 
- - - -
* You have to use docker compose.  
* Write your own Dockerfiles, one per service.  
* The Dockerfiles must be called in your docker-compose.yml by your Makefile.  
* The containers must be built either from the penultimate stable version of __Alpine__ or __Debian__.  
* Each Docker image must have the same name as its corresponding service.  
* Each service has to run in a dedicated container.  

> __You have to build yourself the Docker images of your project.  
It is then forbidden to pull ready-made Docker images.  
As well as using services such as DockerHub  
(Alpine/Debian being excluded from this rule).__  


## Requirements
- - - -
• A Docker container that contains NGINX with TLSv1.2 or TLSv1.3 only.  
• A Docker container that contains WordPress + php-fpm (it must be installed and configured) only.  
• A Docker container that contains MariaDB only.  
• A volume that contains your WordPress database.  
• A second volume that contains your WordPress website files.  
• A docker-network that establishes the connection between your containers.  


- - - - 
Here is an example diagram of the expected result:  
<p> 
<img src="https://github.com/sumxtx/Inception/blob/main/assets/2024-09-28_19-34.png" width="100%" height="50%" position="center">
</p>

## Further Considerations
- - - -
> Docker container is not a virtual machine.  
It is not recommended to use any hacky patch based on ’tail -f’ and so forth when trying to run it.  
Read about how daemons work and whether it’s a good idea to use them or not

> Read about PID 1 and the best practices for writing Dockerfiles.

> To make things simpler, you have to configure your domain name so it points to your local IP address.  
This domain name must be login.42.fr. Again, you have to use your own login.  
For example, if your login is wil, wil.42.fr will redirect to the IP address pointing to wil’s website.  

> Your volumes will be available in the /home/login/data folder of the host machine using Docker.  
Of course, you have to replace the login with yours.

> Using network:, host, or --link, or links:, is forbidden.  
The network line must be present in your docker-compose.yml file.
 
> Your containers musn’t be started with a command running an infinite loop.  
This also applies to any command used as entrypoint, or used in entrypoint scripts.  
The following are a few prohibited hacky patches: tail -f, bash, sleep infinity, while true.
