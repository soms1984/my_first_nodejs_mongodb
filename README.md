# Docker Node MongoDB Example

> Simple example of a dockerized Node/Mongo app

![Image](https://i.ibb.co/4Fgt31L/demo.gif)

## Quick Start

# To perform swarm stack

# to create local registry

sudo docker service create --name registry --publish published=5000,target=5000 registry:2

docker service ls

curl http://localhost:5000/v2/

# to set up directory and clone this image

sudo mkdir /opt/node_mongo

sudo mkdir /usr/src/app

sudo git clone https://github.com/soms1984/my_first_nodejs_mongodb.git /opt/node_mongo

# to test it in the local docker without swarm

cd /opt/node_mongo

sudo docker-compose up -d

sudo docker-compose ls

curl localhost
curl localhost:27017
curl localhost:8080

sudo docker-compose down --volumes

# to perform stack swarm

sudo docker-compose push

sudo docker stack deploy --compose-file docker-compose.yml node_mongo

# remove swarm

sudo docker stack rm node_mongo

```bash
# Run in Docker
docker-compose up
# use -d flag to run in background

# Tear down
docker-compose down

# To be able to edit files, add volume to compose file
volumes: ['./:/usr/src/app']

# To re-build
docker-compose build
```
