# Final project
# docker-compose
This is a repository with final project about docker-compose

In this repository is setted the next services:

1. Jenkins
1. Nexus
1. pythonappVZ
1. Postgres
1. Sonarqube

## Requirements
1. docker
1. docker-compose

## Verify the requirements
Run the next commands:

Input:
```
docker --version
```
Output:
```
Docker version 20.10.7, build f0df350
```

Input:
```
docker-compose -version
```
Output:
```
docker-compose version 1.29.2, build 5becea4c
```
## Run the containers
Clone the repository and run the command:
```
docker-compose up -d
```

## Stop the containers
Inside the folder you cloned the repository and run the next command:
```
docker-compose down
```

## Verify if the containers are running
After run the cantainers with **docker-compose up -d** verify the containers are runnig with:
```
docker ps
```
Output:
```
CONTAINER ID   IMAGE                                    COMMAND                  CREATED         STATUS         PORTS                                                                                      NAMES
65289341a0c3   sonarqube                                "bin/run.sh bin/sona…"   4 minutes ago   Up 4 minutes   0.0.0.0:9000->9000/tcp, :::9000->9000/tcp                                                  sonarqube_compose_vz
be73bb08788e   postgres                                 "docker-entrypoint.s…"   4 minutes ago   Up 4 minutes   5432/tcp                                                                                   postgres_db_vz
0adfbd0f5359   vzamorano/multistagevz:vivian.zamorano   "flask run --port=90…"   4 minutes ago   Up 4 minutes   0.0.0.0:9001->9001/tcp, :::9001->9001/tcp                                                  pythonapp_compose_vz
31351210a566   sonatype/nexus3                          "sh -c ${SONATYPE_DI…"   4 minutes ago   Up 4 minutes   0.0.0.0:8081->8081/tcp, :::8081->8081/tcp                                                  nexus_compose_vz
02a21718ec1b   jenkins/jenkins                          "/sbin/tini -- /usr/…"   4 minutes ago   Up 4 minutes   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp, 0.0.0.0:50000->50000/tcp, :::50000->50000/tcp   jenkins_compose_vz

```

## Verify the applications in the browser
Open your web browser and enter the following URLs:
1. Jenkins:
```
localhost:8080
```
2. Nexus:
```
localhost:8081
```
3. pythonappVZ:
```
localhost:9001
```
4. EndPoint of Python App:
```
localhost:9001/dockerEndpoint
```
5. Sonarqube:
```
localhost:9000
```