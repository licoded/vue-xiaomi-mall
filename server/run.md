> From https://github.com/hai-27/store-server

### Start MySQL Docker

> Reference: https://hub.docker.com/_/mysql

```bash
docker start <container_id>
```

### Edit MySQL Configuration

Reference: [彻底解决mysql中文乱码](https://blog.csdn.net/u012410733/article/details/61619656)

> Configuration File Path: `/etc/mysql/mysql.conf.d/mysqld.cnf`

```ini
[mysqld]
character-set-server=utf8
[client]
default-character-set=utf8
[mysql]
default-character-set=utf8
```

### Import SQLs

```bash
docker cp <host-path> <container_name>:<container_path>
docker exec -it <container_name> bash

mysql -u<username> -p<password>
source storeDB.sql

mysql -u<username> -p<password> storeDB < analogDataSql.sql
```

And edit MySQL connection information in `config.js` file