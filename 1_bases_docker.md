
docker pull postgres
docker container run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
docker container run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres

## first version
docker container run \
--name postgres-alpha \
-e POSTGRES_PASSWORD=mypass1 \
-dp 5432:5432 \
postgres

## second version
docker container run \
--name postgres-beta \
-e POSTGRES_PASSWORD=mypass2 \
-dp 5433:5432 \
postgres:14-alpine3.17



# logs
docker container run \
-e MARIADB_RANDOM_ROOT_PASSWORD=yes \
-dp 3306:3306 \
mariadb:jammy

docker container logs <container_id>
GENERATED ROOT PASSWORD: CW%!]47iU+{3?;@p&2<cSeY!gwn#Q{;z