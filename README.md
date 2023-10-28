
## docker

- Start services

```sh
cd db
docker compose up
```

## oracle

```
user: sys
pass: oracle
db: xe
```

```sql
grant connect ,resource to hr;

ALTER USER hr account unlock
```


## postgres
```sh
POSTGRES_USER: postgres
POSTGRES_PASSWORD: Welcome123
HOST: localhost
```

## extraction

```
cd ext
pip install meltano
meltano add extractor tap-oracle
meltano add loader target-postgres
```

### run

make sure `LD_LIBRARY_PATH` is set for oracle.

```sh
# in ext folder
meltano run tap-oracle target-postgres
# this will ext-load all tables in hr to postgres
```
