# pg-es-fdw-docker
POC on PostgreSQL Elasticsearch Foreign Data Wrapper (with Docker)
PostgreSQL Elasticsearch Foreign Data Wrapper is from https://github.com/Mikulas/pg-es-fdw

## Build
    docker-compose build

## Run
    docker-compose --x-networking up -d
It will run ElasticSearch on port 9200 on the host machine
