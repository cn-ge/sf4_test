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