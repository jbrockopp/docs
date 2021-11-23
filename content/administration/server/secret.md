---
title: "Secret"
linkTitle: "Secret"
description: >
  This section contains information on the secret component for the Vela server.
---

This component is responsible for storing sensitive application [data at rest](https://en.wikipedia.org/wiki/Data_at_rest).

## Configuration

The following options are used to configure the component:

| Name                       | Description                                                                  | Environment Variables                                         |
| -------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------- |
| `secret.vault.addr`        | fully qualified url to the HashiCorp Vault instance                          | `SECRET_VAULT_ADDR`<br>`VELA_SECRET_VAULT_ADDR`               |
| `secret.vault.auth-method` | authentication method used to obtain token from the HashiCorp Vault instance | `SECRET_VAULT_AUTH_METHOD`<br>`VELA_SECRET_VAULT_AUTH_METHOD` |
| `secret.vault.aws-role`    | HashiCorp Vault role used to connect to the auth/aws/login endpoint          | `SECRET_VAULT_AWS_ROLE`<br>`VELA_SECRET_VAULT_AWS_ROLE`       |
| `secret.vault.driver`      | enables HashiCorp Vault as a secret engine                                   | `SECRET_VAULT`<br>`VELA_SECRET_VAULT`                         |
| `secret.vault.prefix`      | prefix for k/v secrets in the HashiCorp Vault instance                       | `SECRET_VAULT_PREFIX`<br>`VELA_SECRET_VAULT_PREFIX`           |
| `secret.vault.renewal`     | frequency to renew the token for the HashiCorp Vault instance                | `SECRET_VAULT_RENEWAL`<br>`VELA_SECRET_VAULT_RENEWAL`         |
| `secret.vault.token`       | token required to access the HashiCorp Vault instance                        | `SECRET_VAULT_TOKEN`<br>`VELA_SECRET_VAULT_TOKEN`             |
| `secret.vault.version`     | version for the k/v backend for the HashiCorp Vault instance                 | `SECRET_VAULT_VERSION`<br>`VELA_SECRET_VAULT_VERSION`         |

## Drivers

The following drivers are available to configure the component:

| Name    | Description                                                        | Documentation                |
| ------- | ------------------------------------------------------------------ | ---------------------------- |
| `vault` | uses a HashiCorp Vault instance for storing sensitive data at rest | https://www.vaultproject.io/ |