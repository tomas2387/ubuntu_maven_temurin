
   

## Docker Pull Command

```docker pull tomas2387/ubuntu_maven_temurin```

## Example docker-compose.yml
```
version: '3.7'
services:
  app:
    build: tomas2387/ubuntu_maven_temurin:21
    tty: true           # <-- This option is required to run the container forever
    volumes:
      - .:/opt/my_awesome_spring_app
    ports:
      - "8080:8080"
```

## Example Dockerfile
```
FROM tomas2387/ubuntu_maven_temurin:20

ENV APP_DIR=/opt/my_awesome_spring_app
WORKDIR $APP_DIR

COPY . .

# port 8080 for the web server
EXPOSE 8080

CMD ["mvn", "spring-boot:run"]
```
