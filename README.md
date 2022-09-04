# Spring users clean-api
Simple api made with spring boot and Clean Architecture.

## How do i run this project? 
In order to run this project, you must have some postgres database running, thankfully you can do that 
quite easily by running the following docker commands

### Start docker postgres container
You can start a new postgres container using docker by simply using the command below. It will create 
a docker container which will listen on port 5432 and will require no authentication for connecting. 
Please note that, this is fine for testing and learning, but if you wanna deploy a project, you ought 
set up some sort of authentication!

```bash
sudo docker run --name postgres --rm -p 5432:5432 -e POSTGRES_HOST_AUTH_METHOD=trust postgres:14-alpine
```

### Enter create users database on the postgres

Once you have created the container, you can create the *uses* database in it, by running the command: 

```bash
sudo docker exec postgres psql -U postgres -c "CREATE DATABASE users;"
```

After that, you are good to go, just install all required dependencies using mvn: 

```bash
mvn install 
```

And then finally run your api:

```bash
mvn spring-boot:run 
```

After a while your api should be up and running, it will be available at.

> http://localhost:8080/api/v1/<optional resource>
