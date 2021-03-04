Followed code on https://github.com/Java-Techie-jt/spring-boot-dockerize & 
https://www.youtube.com/watch?v=e3YERpG2rMs&t=307s&ab_channel=JavaTechie

#Used springtools suite sts 4.9.0 for development

Docker commands
---------------

docker build -t pb2021/spring-boot-rest-docker-demo .
9090 = host port, 8080 port exposed in docker file for the docker image
docker run -p 9090:8080 pb2021/spring-boot-rest-docker-demo



docker tag pb2021/spring-boot-rest-docker-demo:latest spring-boot-rest-docker-demo:latest

docker push pb2021/spring-boot-rest-docker-demo:latest

docker pull pb2021/spring-boot-rest-docker-demo:latest

To delete all dangling containers and images
**docker system prune -a**


In Git Bash or Bash for Windows you can use this Linux command:

docker stop $(docker ps -q)
For PowerShell, the command is very similar to the Linux one:

docker ps -q | % { docker stop $_ }




Below commands with $ placeholders run in Git Bash or Bash for Windows you can use this Linux command:
# Delete every Docker containers
# Must be run first because images are attached to containers
docker rm -f $(docker ps -a -q)
or in powershell

docker ps -a -q | % { docker rm -f $_ }


# Delete every Docker image
docker rmi -f $(docker images -q)
or in powershell

docker images -q | % { docker rmi -f $_ }
