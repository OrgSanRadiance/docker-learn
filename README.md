# docker-learn

Example here is a "Login and Registration Project Using Flask and MySQL"

Two application hosted on two individual container , connected on a private docker network
App1 : Python Flask WSGI "helloapp.py" 
App2 : MySQL server that store user infromation

Procedure to deploy App containers
----------------------------------
- App2: MySQL databased container

  1. pull the existing  MySQL server container image from the public dockerhub registry

     $ docker pull mysql:latest
  3. Run the container image mysql:latest with defined paramaters

     $ docker run --name hello-app-database -p 3306:3306  -e MYSQL_ROOT_PASSWORD='rootlogin@123' -e MYSQL_DATABASE='geeklogin' -v sqldata:/var/lib/mysql -d mysql:latest

- App1: Python Flask "helloapp.py"
  
Build docker Image
1. Create "Dockerfile"  as example
2. Build docker image with application code as below

   $ docker build -t helloapp:v2.0.1 .
4. Run the created image to deploy the application

   $ docker run --name hello-app-v2 --net=host -d helloapp:v2.0.1

Additional Commands
1. Check running container

   $ docker ps

3. Check container running logs

   $ docker logs -f <container name>

5. Login to the container terminal

   $ docker exec -it <container name> /bin/sh
