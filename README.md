# C0884039_ClassAssignment_3# Creating Docker Image from Node + Express Application

### Create Node Express Application: https://github.com/imanmeet-24/C0884039_ClassAssignment_3

### Create Dockerfile in the project and copy the following code in the file

```
# syntax=docker/dockerfile:1
FROM node:18-alpine
LABEL maintainer "imanmeet24@gmail.com"
LABEL build_date "2024-02-06"
WORKDIR /app
COPY . .
RUN npm install
EXPOSE 3000
CMD ["node", "app.js"]
```

### Create Docker Image using following command

```
docker build --tag c0884039-node-assignment3 .
docker images
```

### Run the created Image using below commands

```
docker run --detach --publish 3000:3000 c0883191-node-assignment3:latest
docker run --detach --publish 3001:3000 c0883191-node-assignment3:latest
docker ps
```

### Stop container using below commands

```
docker stop determined_proskuriakova
docker stop pensive_antonelli
docker ps
docker ps -a
```

### Remove existing continers using below commands

```
docker rm 2b85acbe2eca
docker rm 98f12c58ce44
docker ps -a
```

### Run the continers using environment variables

```
docker run --detach --publish 3000:80 -e PORT=80 c0884039-node-assignment3:latest
docker run --detach --publish 3000:80 -e PORT=80 -e NAME=C1 c0884039-node-assignment3:latest
docker run --detach --publish 3001:8080 -e PORT=8080 -e NAME=C1 c0884039-node-assignment3:latest
```

### Run the continers using environment variables using file

```
docker run --detach --publish 3000:3000 --env-file my-env.txt c0884039-node-assignment3:latest
```

### Tag your recently created image to publish on DockerHub registry

```
docker image tag c0884039-node-assignment3:latest imanmeet-24/c0884039-node-assignment3:1.0.0
docker images
docker login
docker push imanmeet-24/c0884039-node-assignment3:1.0.0
```
### Pull and run the recently pushed image on local docker environment
```
docker pull imanmeet-24/c0884039-node-assignment3:1.0.0
docker run -d -p 3000:3000 imanmeet-24/c0883191-node-assignment3:1.0.0
```