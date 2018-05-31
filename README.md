# springboot-docker

# Building
The Spring Pet Clinic image can now be built using the following command-line:

docker build --build-arg
```
url=https://github.com/spring-projects/spring-petclinic.git\
  --build-arg project=spring-petclinic\
  --build-arg artifactid=spring-petclinic\
  --build-arg version=1.5.1\
  -t houssoli/spring-petclinic - < Dockerfile
```
Since the image doesn’t depend on the filesystem, no context needs to be passed and the Dockerfile can be piped from the standard input.

To build another app, parameters can be changed accordingly e.g.:
```
docker build --build-arg url=https://github.com/heroku/java-getting-started.git\
  --build-arg project=java-getting-started\
  --build-arg artifactid=java-getting-started\
  --build-arg version=1.0\
  -t houssoli/java-getting-started - < Dockerfile
```
# Running
Running an image built with the above command is quite easy:
```
docker run -ti -p8080:8080 houssoli/spring-petclinic
```
Running the second image uses a different port, so the command should be:
```
docker run -ti -p8080:5000 houssoli/java-getting-started
```
# For more details, have a look to the original blog posts from Nicolas Fränkel at :
* [Dockerfile Maven-based Github projects](https://blog.frankel.ch/dockerfile-maven-based-github-projects/)
* [Strategies for optimizing Maven Docker images](https://blog.frankel.ch/strategies-optimizing-docker-maven-image/)
