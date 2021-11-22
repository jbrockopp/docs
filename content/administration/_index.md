---
title: "Administration"
linkTitle: "Administration"
layout: administration
description: >
  This section contains information on installing and administering Vela.
menu:
  main:
    weight: 5
---

Vela is an on-premises Pipeline Automation (CI/CD) platform...

TODO: add image

## Database

Vela requires integration with a database system in order to store [data at rest](https://en.wikipedia.org/wiki/Data_at_rest).

The following database systems are supported by Vela:

| Name         | Documentation               | Minimum Supported Version |
| ------------ | --------------------------- | ------------------------- |
| `SQLite`     | https://www.sqlite.org/     | `TODO`                    |
| `PostgreSQL` | https://www.postgresql.org/ | `TODO`                    |

## Queue

Vela requires integration with a queue system in order to manage workloads to be executed.

The following queue systems are supported by Vela:

| Name    | Documentation     | Minimum Supported Version |
| ------- | ----------------- | ------------------------- |
| `Redis` | https://redis.io/ | `TODO`                    |

## Source Control

Vela requires integration with a source control management (SCM) system in order to retrieve source code.

The following source control management systems are supported by Vela:

| Name     | Documentation             | Minimum Supported Version |
| -------- | ------------------------- | ------------------------- |
| `GitHub` | https://github.com/about/ | `TODO`                    |
