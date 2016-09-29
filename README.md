docker-oracle-xe-11g
============================

Oracle Express Edition 11g Release 2 on Debian Jessie 8.6

_Based on wnameless/oracle-xe-11g/ docker image_ 

This **Dockerfile** is a [trusted build](https://registry.hub.docker.com/u/brunodias20/oracle-xe-11g/) of [Docker Registry](https://registry.hub.docker.com/).

### Installation(with Debian Jessie 8.6)
```
docker pull wnameless/oracle-xe-11g
```

Run with 1521 ports opened:
```
docker run -p 1521:1521 brunodias20/oracle-xe-11g
```

Run this, if you want the database to be connected remotely:
```
docker run -d -p 1521:1521 -e ORACLE_ALLOW_REMOTE=true brunodias20/oracle-xe-11g
```

Password for SYS & SYSTEM
```
oracle
```

Password for dbuser
```
us3rdb
```

Support custom DB Initialization, create db for example
```
# Dockerfile 
FROM brunodias20/oracle-xe-11g

ADD create-db.sql /docker-entrypoint-initdb.d/
```
