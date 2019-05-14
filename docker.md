## DOCKER

[Docker] Remove all Docker volumes to delete the database

Radu Raicea edited this page on 30 Sep 2017 · 1 revision
If anything happens to the database and you can't seem to fix it, it might be best to completely delete the Docker volumes holding the database and recreating them.

### Deleting all the containers

Before deleting the volumes, you need to delete all the existing containers using the following command (make sure the application is not running)

`$ docker rm $(docker ps -a -q) -f`

### Deleting all the volumes

Once all the containers are deleted, you can delete all the Docker volumes on your computer using the following command

`$ docker volume prune`

If you don't want to delete all the Docker volumes on your computer, you can search for a specific one and deleting it

`$ docker volume ls`

`$ docker volume rm <name_of_volume>`

### Recreating the volumes

Recreating the volumes is as simple as restarting the application

`$ docker-compose up --build`


## DOCKER COMPOSE

`docker-compose up` launch services in docker-compose.yml

`docker-compose up -d` launch services in docker-compose.yml with keeping hand on terminal

`docker-compose up –build` re-build services before launch

`docker-compose down` stop services

`docker-compose restart` re-launch all services

`docker-compose restart name_of_service` re-launch a service

`docker-compose exec rails bash` bash console in the rails container

`docker-compose exec rails bin/rails db:migrate` execute a rails db:migrate in rails container

`docker-compose logs` all services logs from last launch and give back hand on terminal

`docker-compose logs -f` listening all services logs from last launch without giving back hand on terminal

`docker-compose logs -f rails` listening rails service logs from last launch without giving back hand on terminal
