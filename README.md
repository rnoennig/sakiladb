# How to build
docker build .

# How to run
docker run --name sakila-mariadb -e MYSQL_ROOT_PASSWORD=root -d <imagename>

# How to connect
SAKILADB\_IP=$(docker inspect sakila-mariadb --format '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}')
mysql -u root -p -h $SAKILADB_IP -e "select count(*) from sakila.film;"
