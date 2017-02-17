# How to build
docker build .

# How to run
docker run --name sakiladb --env MYSQL_ROOT_PASSWORD=root --detach rnoennig/sakiladb

# How to use/connect
SAKILADB\_IP=$(docker inspect sakiladb --format '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}')
mysql --user root --password --host $SAKILADB_IP --exec "select count(*) from sakila.film;"
