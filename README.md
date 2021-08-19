# Redbee Academy - Liquibase


## Comenzar


### Iniciar base de datos PostgreSQL

```sh
docker run --rm --name tmp_postgres -p 5432:5432 -e POSTGRES_PASSWORD=academy postgres:11-alpine
```


### Aplicar cambios con Liquibase

```sh
docker run --rm -v $(pwd):/liquibase/changelog --link tmp_postgres liquibase/liquibase:4.4 --defaultsFile=/liquibase/changelog/liquibase.properties update
```


### Realizar rollback a un tag específico con Liquibase

```sh
docker run --rm -v $(pwd):/liquibase/changelog --link tmp_postgres liquibase/liquibase:4.4 --defaultsFile=/liquibase/changelog/liquibase.properties rollback v1.1
```


### Generar changelog de una base de datos existente con Liquibase

```sh
docker run --rm -v $(pwd):/liquibase/changelog --link tmp_postgres liquibase/liquibase:4.4 --defaultsFile=/liquibase/changelog/liquibase.properties generateChangeLog
```


## Referencias


- [Liquibase](https://www.liquibase.org/)
- [Liquibase's change types](https://docs.liquibase.com/change-types/community/home.html)
- [Liquibase's commands](https://docs.liquibase.com/commands/community/home.html)
- [Liquibase official Docker image](https://hub.docker.com/r/liquibase/liquibase)
