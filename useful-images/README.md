
# To connect PHPMyAdmin and MySQL Server

## Create a network
```
docker network create asgard
```

## MySQL Server

```
docker run --name mysql1 -e MYSQL_ROOT_PASSWORD=root --network asgard -p 3306:3306 -d mysql:5.7.35

```

## PHPMyAdmin

```
docker run --name phpmyadmin1 -e PMA_HOST=mysql1 --network asgard -p 9090:80 -d phpmyadmin

```