---
title: "Secret"
linkTitle: "Secret"
description: >
  This section contains information on the secret component for the Vela server.
---

This component is responsible for storing sensitive application [data at rest](https://en.wikipedia.org/wiki/Data_at_rest).

## Configuration

The following options are used to configure the component:

| Name           | Environment          | Description                                   |
| -------------- | -------------------- | --------------------------------------------- |
| `vault.driver` | `SECRET_VAULT`       | enables the Vault secret engine               |
| `vault.addr`   | `SECRET_VAULT_ADDR`  | full navigatable url to Vault installation    |
| `vault.token`  | `SECRET_VAULT_TOKEN` | token required to read/write secrets to Vault |

{{% alert color="info" %}}
All available options support `VELA_*` prefixes for the environment variables. For example:

- `SECRET_VAULT` - enables the Vault secret engine
- `VELA_SECRET_VAULT` - enables the Vault secret engine
  {{% /alert %}}

## Drivers

The following drivers are available to configure the component:

| Name    | Description                      | Documentation            |
| ------- | -------------------------------- | ------------------------ |
| `redis` | uses a Redis queue for workloads | https://redis.io         |