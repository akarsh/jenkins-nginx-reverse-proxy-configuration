# jenkins-nginx-reverse-proxy-configuration

This project contains a docker-compose yaml file which is targeted towards users of arm64 architecture M1 Mac

# Jenkins: Reverse proxy - Nginx 

The docker-compose yaml file contains Nginx and Jenkins docker images.

## Docker network: jenkins-net

Docker network needs to be created in order to interconnect Nginx and Jenkins docker containers.

```
docker network create --driver bridge jenkins-net
```

## Add host jenkins.example.com to /etc/hosts file

You need to make change in the file /etc/hosts and add 
```
127.0.0.1 jenkins.example.com
```
to /etc/hosts file.

## Build and run

For detached execution docker-compose yaml file execute

```
docker-compose -f docker-compose.yaml up -d
```

Jenkins will be running on host url: http://jenkins.example.com

## Stop

To stop the selenium-hub container execute

```
docker-compose -f docker-compose.yaml down
```
