# Docker service for MYSQL

Clone this Repository and Run below command :


mkdir -p /my_drive/mysql_docker/data
mkdir -p /my_drive/mysql_docker/conf

Copy my.cnf to /my_drive/mysql_docker/conf

Run Below Docker command

docker  -H unix:///var/run/docker.sock service create -p 3306:3306 --env MYSQL_ROOT_PASSWORD=my-secret-pw --container-label environment=prod  --label environment=prod --mount type=bind,src=/my_drive/mysql_docker/conf,dst=/etc/mysql/conf.d  --mount type=bind,src=/my_drive/mysql_docker/data,dst=/var/lib/mysql   --detach=true --hostname mysql  --name mysql --limit-memory 2.2G  mysql:latest

# Mount Point
"/my_drive/mysql_docker/data", "/my_drive/mysql_docker/conf"

# Exposed Port
3306

