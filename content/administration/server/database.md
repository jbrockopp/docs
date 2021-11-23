---
title: "Database"
linkTitle: "Database"
description: >
  This section contains information on the database component for the Vela server.
---

This component is responsible for storing application [data at rest](https://en.wikipedia.org/wiki/Data_at_rest).

This data is an organized collection of information necessary for the platform to operate.

## Configuration

The following options are used to configure the component:

| Name                         | Description                                                      | Required | Default       | Environment Variables                                             |
| ---------------------------- | ---------------------------------------------------------------- | -------- | ------------- | ----------------------------------------------------------------- |
| `database.addr`              | full connection string to the database                           | `true`   | `sqlite3`     | `DATABASE_ADDR`<br>`VELA_DATABASE_ADDR`                           |
| `database.driver`            | type of client to control and operate the database               | `true`   | `vela.sqlite` | `DATABASE_DRIVER`<br>`VELA_DATABASE_DRIVER`                       |
| `database.compression.level` | level of compression for logs stored in the database             | `true`   | `3`           | `DATABASE_COMPRESSION_LEVEL`<br>`VELA_DATABASE_COMPRESSION_LEVEL` |
| `database.connection.open`   | maximum number of open connections to the database               | `true`   | `0`           | `DATABASE_CONNECTION_OPEN`<br>`VELA_DATABASE_CONNECTION_OPEN`     |
| `database.connection.idle`   | maximum number of idle connections to the database               | `true`   | `2`           | `DATABASE_CONNECTION_IDLE`<br>`VELA_DATABASE_CONNECTION_IDLE`     |
| `database.connection.life`   | duration of time a connection is reusable                        | `true`   | `30m`         | `DATABASE_CONNECTION_LIFE`<br>`VELA_DATABASE_CONNECTION_LIFE`     |
| `database.encryption.key`    | AES-256 key for encrypting/decrypting values in the database     | `true`   | `N/A`         | `DATABASE_ENCRYPTION_KEY`<br>`VELA_DATABASE_ENCRYPTION_KEY`       |
| `database.skip_creation`     | skips the creation of tables and indexes in the database         | `false`  | `false`       | `DATABASE_SKIP_CREATION`<br>`VELA_DATABASE_SKIP_CREATION`         |

## Drivers

The following drivers are available to configure the component:

| Name       | Description                                         | Documentation              |
| ---------- | --------------------------------------------------- | -------------------------- |
| `sqlite3`  | uses a SQLite database for storing data at rest     | https://www.sqlite.org     |
| `postgres` | uses a PostgreSQL database for storing data at rest | https://www.postgresql.org |