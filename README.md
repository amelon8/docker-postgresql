# docker-postgresql

- Bring up the Docker container. Verify if container is running.

```
docker-compose up -d
docker-compose ps
```

- Enter the container shell.

```
docker-compose exec postgresql sh
```

- Run psql (user: `postgres`, password: `<env POSTGRESQL_PASSWORD>` - see `docker-compose.yaml`)

```
% psql
postgres=# \l
                                                     List of databases
   Name    |  Owner   | Encoding | Locale Provider |   Collate   |    Ctype    | Locale | ICU Rules |   Access privileges
-----------+----------+----------+-----------------+-------------+-------------+--------+-----------+-----------------------
 postgres  | postgres | UTF8     | libc            | en_US.UTF-8 | en_US.UTF-8 |        |           |
 template0 | postgres | UTF8     | libc            | en_US.UTF-8 | en_US.UTF-8 |        |           | =c/postgres          +
           |          |          |                 |             |             |        |           | postgres=CTc/postgres
 template1 | postgres | UTF8     | libc            | en_US.UTF-8 | en_US.UTF-8 |        |           | =c/postgres          +
           |          |          |                 |             |             |        |           | postgres=CTc/postgres
(3 rows)
```

- Stop the container.

```
docker-compose down
```

## pgadmin4

### Configure DB connection*
* Server Name: `postgresql`
* Host name/address: `postgresql`
* Port: 5432
* Database: `facebook`
* User: `postgres`
* Password: `<env POSTGRESQL_PASSWORD>`

### pgadmin4 UI
* http://localhost:10009
