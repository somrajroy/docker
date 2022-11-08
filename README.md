# docker <br/>
Exercise to create a Mongodb/NodeJS app with data persistence.

* Clone the repository to your localmachine <br/>
* Build the frontend image with below command <br/>
  $ docker build -t mongoapp . <br/>
* Run docker compose to create Mongodb and Mongoexpress <br/>
  $ docker-compose up -d
* Goto Mongo express : http://localhost:8080 <br/>
* Create a database in Mongodb as "my-db" <br/>
* Create a collection "users" <br/>
  $ docker run --name mongoapp --network jsmongodb-app_default -dp 3000:3000 mongoapp <br/>
* Visit the local webpage at http://localhost:3000
  You can update the data and verify that data is persisting even after container restarts/deletion (Delete the mongoapp container and create a new one to verify) <br/>
* Clear everything
  $ docker rm -f mongoapp <br/>
  $ docker-compose down <br/>
  $ docker-compose down --volume <br/><br/>
  
# Exercise
* In this demo we are creating the frontend with a Dokerfile and the backend with a docker compose file (Mongodb + Mongoexpress). However we can put everything together in docker compose file. We can then create & destroy everything with single command (docker-compose down). <br/>
* Please create an end to end docker compose file by the weekend and share with me.
