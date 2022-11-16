# docker <br/>
<ins> Create a Mongodb/NodeJS app with data persistence.</ins> <br/> <br/>
This covers docker networking, volumes, Docker registries, Image/Container management and Docker compose.<br/> 

#### Workflow/Architecture <br/>
![image](https://user-images.githubusercontent.com/92582005/202113215-a9494cba-2108-4ee3-8da5-7f92ad2abba9.png) <br/>
![image](https://user-images.githubusercontent.com/92582005/202115266-2e2d0ecf-f943-4b34-af28-cd9c5efef8f2.png) <br/>

## Steps to be followed <br/>
* Clone the repository to your localmachine <br/>
* Build the frontend image with below command <br/>
  $ docker build -t mongoapp . <br/>
* Tag the image and upload in Docker hub. (optional step) <br/>
  $ docker tag mongoapp <<-your-dockerhub-username->>/mongoapp:1.0 <br/>
  $ docker push <<-your-dockerhub-username->>/mongoapp:1.0 <br/>
* Run docker compose to create Mongodb and Mongoexpress <br/>
  $ docker-compose up -d
* Goto Mongo express : http://localhost:8080 <br/>
* Create a database in Mongodb as "my-db" <br/>
* Create a collection "users" <br/>
* Create the frontend container with below command using the image created in 1st step. (Please debug minor issues if there are any & start the container. You can also pull the image from docker hub where you uploaded the image earlier) <br/>
  $ docker run --name mongoapp --network docker_default -dp 3000:3000 mongoapp <br/>
* Visit the local webpage at http://localhost:3000
  You can update the data and verify that data is persisting even after container restarts/deletion (You may delete the mongoapp container and create a new one to verify data persistence) <br/>
* Clear everything
  $ docker rm -f mongoapp <br/>
  $ docker-compose down <br/>
  $ docker-compose down --volume <br/><br/>
  
# Exercise
* In this demo we are creating the frontend with a Dokerfile and the backend with a docker compose file (Mongodb + Mongoexpress). However we can put everything together in docker compose file. We can then create & destroy everything with single command (docker-compose down). <br/>
* Please create an end to end docker compose file by the weekend and share with me.
