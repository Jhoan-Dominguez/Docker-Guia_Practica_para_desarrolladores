
# volume and network

docker container run \
-dp 3306:3306 \
--name world-db \
--env MARIADB_USER=world-user \
--env MARIADB_PASSWORD=world-password \
--env MARIADB_ROOT_PASSWORD=root-secret-password \
--env MARIADB_DATABASE=world-db \
--volume world-db:/var/lib/mysql \
--network world-app \
mariadb:jammy
<!-- --env MARIADB_PASSWORD=user-password \ -->


docker container run \
--name phpmyadmin \
-dp 8080:80 \
-e PMA_ARBITRARY=1 \
--network world-app \
phpmyadmin:5.2.0-apache


# bind volume
docker container run \
--name nest-app \
-d \
-w /app \
-p 80:3000 \
-v "$(pwd)":/app \
node:18-alpine3.16 \
sh -c "yarn install && yarn start:dev"

# terminal interactiva
docker exec -it 186 /bin/sh