# SQL

(!) Seems like MySQL Docker image doesn't run properly on Raspberry Pi.

## PostgreSQL

```
docker run --name notot -p 5432:5432 -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```

## Backup

```
docker exec -t d0d0754d43c9 pg*dumpall -c -U postgres > dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql
```

https://stackoverflow.com/questions/24718706/backup-restore-a-dockerized-postgresql-database

```
scp pi@rxtl.local:/home/pi/dump_10-06-2022_12_41_59.sql ./
```
