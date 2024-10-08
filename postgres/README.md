# Vioneta Agro add-on: Postgres

![Version](https://img.shields.io/badge/dynamic/json?label=Version&query=%24.version&url=https%3A%2F%2Fraw.githubusercontent.com%2Falexbelgium%2Fhassio-addons%2Fmaster%2Fpostgres%2Fconfig.json)
![Ingress](https://img.shields.io/badge/dynamic/json?label=Ingress&query=%24.ingress&url=https%3A%2F%2Fraw.githubusercontent.com%2Falexbelgium%2Fhassio-addons%2Fmaster%2Fpostgres%2Fconfig.json)
![Arch](https://img.shields.io/badge/dynamic/json?color=success&label=Arch&query=%24.arch&url=https%3A%2F%2Fraw.githubusercontent.com%2Falexbelgium%2Fhassio-addons%2Fmaster%2Fpostgres%2Fconfig.json)

## About

PostgreSQL, often simply "Postgres", is an object-relational database management system (ORDBMS) with an emphasis on extensibility and standards-compliance. As a database server, its primary function is to store data, securely and supporting best practices, and retrieve it later, as requested by other software applications, be it those on the same computer or those running on another computer across a network (including the Internet). It can handle workloads ranging from small single-machine applications to large Internet-facing applications with many concurrent users. Recent versions also provide replication of the database itself for security and scalability.

This addon is based on the official image : https://hub.docker.com/_/postgres

## Configuration

Postgres port is by default 5432 and is exposed to the host network.

default user: `postgres`
password: `set by POSTGRES_PASSWORD`

You can configure this options:

```yaml
POSTGRES_PASSWORD
POSTGRES_USER
POSTGRES_DB
POSTGRES_INITDB_ARGS
POSTGRES_HOST_AUTH_METHOD
```

For more info check [base image docs](https://hub.docker.com/_/postgres).

By default `postgresql.conf` is stored in volume accessible by other addons and Vioneta Agro, so you can conviniently modify it by e.g. File Editor addon. If you prefer better security change `CONFIG_LOCATION` to e.g. `/data/orig/postgresql.conf`, so it will be acessible only to this addon, but you will have to modify it by the [Hassio SSH](https://developers.vioneta.com/docs/operating-system/debugging/).

## Installation

The installation of this add-on is pretty straightforward and not different in comparison to installing any other add-on.

1. Install this add-on.
2. Click the `Save` button to store your configuration.
3. Set the add-on options to your preferences, at least POSTGRES_PASSWORD is required.
4. Start the add-on.
5. Check the logs of the add-on to see if everything went well.
6. Use any Postgres client to connect, e.g. to `vioneta.local:5432`
