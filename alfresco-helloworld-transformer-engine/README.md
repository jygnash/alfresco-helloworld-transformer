# Alfresco Hello World Transformer Engine

## Purpose
This is an example Hello World transformer used to demonstrate how to create a simple transformer based on
[alfresco-transform-core](https://github.com/Alfresco/alfresco-transform-core).
The instructions to follow with this example can be found [here](https://github.com/Alfresco/acs-packaging/blob/master/docs/creating-a-t-engine.md).

See the [parent project](https://github.com/Alfresco/alfresco-transform-core) for more information and instructions on how to build & run.

## Prerequisites
* Java 11
* Maven
* Docker

## Build using Maven
The project can be built by running the Maven command:
```bash
mvn clean install -Plocal
```
This will build the project as a Spring Boot fat jar in the {project directory}/target folder
and as a docker image in the local docker registry.

Before proceeding to start the container, confirm that the build was successful and the local docker
registry contains **alfresco/alfresco-helloworld-transformer** image.

## Run in Docker

Execute the following command to run the transformer container in detached mode on port 8090:

```bash
docker run -d -p 8090:8090 --name alfresco-helloworld-transformer alfresco/alfresco-helloworld-transformer:latest
```

> Since this is a Spring Boot application,
 it might be helpful to run it as such during development by either executing `mvn spring-boot:run`
 or `java -jar target/alfresco-helloworld-transformer-{version}.jar` in the project directory.
 The application will be accessible on port 8090.


