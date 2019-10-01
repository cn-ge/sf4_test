
CREATE DOCKER MACHINE : https://docs.docker.com/machine/install-machine/

LISTER LES MACHINES : 
$ docker-machine ls

ACTIVER LA MACHINE : 
$ eval $(docker-machine env default)

CREER UNE MACHINE : 
$ docker-machine create --driver virtualbox default

RECUPERER LES VARIABLES D'ENVIRONNEMENT :
$ docker-machine env default
export DOCKER_TLS_VERIFY="1"
export DOCKER_HOST="tcp://192.168.99.101:2376"
export DOCKER_CERT_PATH="/Users/cgeindreau/.docker/machine/machines/default"
export DOCKER_MACHINE_NAME="default"

CREER LES VARIABLES D'ENVIRONNEMENT :
$ eval "$(docker-machine env default)"


VERIFIER LE STATUT DES MACHINES (active)
$ docker-machine ls 

RECUPERER L'ADRESSE IP DE LA MACHINE :
docker-machine ip default


source : https://medium.com/@romaricp/the-perfect-kit-starter-for-a-symfony-4-project-with-docker-and-php-7-2-fda447b6bca1


Builder les images
$ docker-compose build
Démarrer les containers
$ docker-compose up -d
$ docker container start container_name
Lister les containers (voir leur état)
$ docker ps -a
Supprimer les containers
$ docker container stop container_name
$ docker container rm container_name
Exécuter container mysql (ouvre le container)
$ docker exec -it sf4_mysql bash -l    
, puis
$ mysql -u admin -p
...


phpmyadmin > http://127.0.0.1:8080/index.php
project > http://127.0.0.1