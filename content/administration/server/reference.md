---
title: "Reference"
linkTitle: "Reference"
weight: 2
description: >
  This section contains a reference of the configuration options for the Vela server service.
---

## VELA_ACCESS_TOKEN_DURATION

This should be the duration of time a Vela access token for a user is valid for the server.

The configuration is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `15m`.
{{% /alert %}}

## VELA_ADDR

This should be a fully qualified URL to the Vela [server](/docs/administration/server/) address.

The configuration is required and should be provided as a `string`.

## VELA_COMPILER_GITHUB

This should enable using GitHub Enterprise as a registry for [templates](/docs/tour/templates/) used for the [compiler component](/docs/administration/server/components/compiler/) for the server.

The configuration is optional and should be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `false`.
{{% /alert %}}

## VELA_COMPILER_GITHUB_TOKEN

This should be a [Personal Access Token (PAT)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) for the GitHub Enterprise instance used for the [compiler component](/docs/administration/server/components/compiler/) for the server.

The configuration is optional and should be provided as a `string`.

## VELA_COMPILER_GITHUB_URL

This should be a fully qualified URL to the GitHub Enterprise instance used for the [compiler component](/docs/administration/server/components/compiler/) for the server.

The configuration is optional and should be provided as a `string`.

## VELA_DATABASE_ADDR

This should be a fully qualified URL to the database system used for the [database component](/docs/administration/servere/components/database/) for the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `vela.sqlite`.
{{% /alert %}}

## VELA_DATABASE_COMPRESSION_LEVEL

This should be the level of compression for logs used for the [database component](/docs/administration/server/components/database/) for the server.

The configuration is required and should be provided as a `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `3`.

The possible options to provide for this variable are:

* `-1`
* `0` - produces no compression for the log data
* `1` - produces compression for the log data the fastest and with the largest size of data
* `2`
* `3`
* `4`
* `5` - produces compression for the log data with an even balance of speed and size of data
* `6`
* `7`
* `8`
* `9` - produces compression for the log data the slowest and with the smallest size of data
{{% /alert %}}

## VELA_DATABASE_CONNECTION_IDLE

This should be the maximum number of idle connections used for the [database component](/docs/administration/server/components/database/) for the server.

The configuration is required and should be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `2`.
{{% /alert %}}

## VELA_DATABASE_CONNECTION_LIFE

This should be the duration of time a connection is reusable for the [database component](/docs/administration/server/components/database/) for the server.

The configuration is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `30m`.
{{% /alert %}}

## VELA_DATABASE_CONNECTION_OPEN

This should be the maximum number of open connections used for the [database component](/docs/administration/server/components/database/) for the server.

The configuration is required and should be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `0` (meaning no limit is set).
{{% /alert %}}

## VELA_DATABASE_DRIVER

This should be the driver used for the [database component](/docs/administration/server/components/database/) for the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `sqlite3`.

The possible options to provide for this variable are:

* `postgres`
* `sqlite3`
{{% /alert %}}

## VELA_DATABASE_ENCRYPTION_KEY

This should set the AES key for encrypting/decrypting values used for the [database component](/docs/administration/server/components/database/) for the server.

The configuration is required and should be provided as an `string`.

## VELA_DATABASE_SKIP_CREATION

This should skip the creation of tables and indexes used for the [database component](/docs/administration/server/components/database/) for the server.

The configuration is optional and should be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `false`.
{{% /alert %}}

## VELA_DEFAULT_BUILD_TIMEOUT

This should be a duration of time that controls the default amount of time a build can run for on a worker.

The configuration is optional and should be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `0`.
{{% /alert %}}

## VELA_DISABLE_WEBHOOK_VALIDATION

This should control if webhooks sent by the SCM to the server should be validated.

The configuration is optional and should be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable should only be used for local development.

This variable has a default value of `false`.
{{% /alert %}}

## VELA_ENABLE_SECURE_COOKIE

This should control if cookies with the secure flag are set by the server.

The configuration is optional and should be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable should only be used for local development.

This variable has a default value of `true`.
{{% /alert %}}

## VELA_MODIFICATION_ADDR

This should be a fully qualified URL to the modification endpoint used for the [compiler component](/docs/administration/server/components/compiler/) for the server.

The configuration is optional and should be provided as a `string`.

## VELA_MODIFICATION_RETRIES

This should be the number of times to resent failed requests to the modification endpoint used for the [compiler component](/docs/administration/server/components/compiler/) for the server.

The configuration is optional and should be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `5`.
{{% /alert %}}

## VELA_MODIFICATION_SECRET

This should be a shared secret for authenticating communication between compiler and the modification endpoint used for the [compiler component](/docs/administration/server/components/compiler/) for the server.

The configuration is optional and should be provided as a `string`.

## VELA_MODIFICATION_TIMEOUT

This should be a fully qualified URL to the modification endpoint used for the [compiler component](/docs/administration/server/components/compiler/) for the server.

The configuration is optional and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `8s`.
{{% /alert %}}

## VELA_PORT

This should set the port the server API listens on for requests.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `8080`.
{{% /alert %}}

## VELA_QUEUE_ADDR

This should be a fully qualified URL to the queue system used for the [queue component](/docs/administration/server/components/queue/) for the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_ADDR` variable](/docs/administration/worker/reference/#vela_queue_addr) provided to the worker.
{{% /alert %}}

## VELA_QUEUE_CLUSTER

This should enable the [queue component](/docs/administration/server/components/queue/) for the server to connect to a cluster rather than a standalone instance.

The configuration is optional and should be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_CLUSTER` variable](/docs/administration/worker/reference/#vela_queue_cluster) provided to the worker.
{{% /alert %}}

## VELA_QUEUE_DRIVER

This should be the driver used for the [queue component](/docs/administration/server/components/queue/) for the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_DRIVER` variable](/docs/administration/worker/reference/#vela_queue_driver) provided to the worker.

The possible options to provide for this variable are:

* `redis`
{{% /alert %}}

## VELA_QUEUE_POP_TIMEOUT

This should be the timeout for requests sent for pushing workloads used for the [queue component](/docs/administration/server/components/queue/) for the server.

The configuration is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `60s`.
{{% /alert %}}

## VELA_QUEUE_ROUTES

This should be the unique channels or topics for pushing workloads used for the [queue component](/docs/administration/server/components/queue/) for the server.

The configuration is required and should be provided as a comma-separated list (i.e. `myRoute1,myRoute2`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `vela`.
{{% /alert %}}

## VELA_REFRESH_TOKEN_DURATION

This should be the duration of time a Vela refresh token for a user is valid for the server.

The configuration is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `8h`.
{{% /alert %}}

## VELA_REPO_ALLOWLIST

This should be a list of repositories in the SCM that can be enabled by the server.

The configuration is optional and should be provided as a comma-separated list (i.e. `myRoute1,myRoute2`).

## VELA_SCM_ADDR

This should be a fully qualified URL to the SCM system used for the [SCM component](/docs/administration/server/components/scm/) for the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `https://github.com`.
{{% /alert %}}

## VELA_SCM_CLIENT

This should be the client ID from the OAuth application from the SCM system used for the [SCM component](/docs/administration/server/components/scm/) for the server.

The configuration is required and should be provided as a `string`.

## VELA_SCM_CONTEXT

This should be the message to set in the commit status on the SCM system used for the [SCM component](/docs/administration/server/components/scm/) for the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `continuous-integration/vela`.
{{% /alert %}}

## VELA_SCM_DRIVER

This should be the driver used for the [SCM component](/docs/administration/server/components/scm/) for the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `github`.

The possible options to provide for this variable are:

* `github`
{{% /alert %}}

## VELA_SCM_SCOPES

This should be the permission scopes to apply for OAuth credentials on the SCM system used for the [SCM component](/docs/administration/server/components/scm/) for the server.

The configuration is required and should be provided as a comma-separated list (i.e. `myScope1,myScope2`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `read:org,read:user,repo,repo:status,user:email`.
{{% /alert %}}

## VELA_SCM_SECRET

This should be the client secret from the OAuth application from the SCM system used for the [SCM component](/docs/administration/server/components/scm/) for the server.

The configuration is required and should be provided as a `string`.

## VELA_SCM_WEBHOOK_ADDR

This should be a fully qualified URL on the SCM system to send webhooks to used for the [SCM component](/docs/administration/server/components/scm/) for the server.

The configuration is optional and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of [the `VELA_ADDR` variable](/docs/administration/server/reference/#vela_addr) provided to the server.
{{% /alert %}}

## VELA_SECRET

This should be a shared secret with the Vela [worker](/docs/administration/worker/) for authenticating communication between workers and the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_SERVER_SECRET` variable](/docs/administration/worker/reference/#vela_server_secret) provided to the worker.
{{% /alert %}}

## VELA_SECRET_VAULT

This should enable using HashiCorp Vault as a secret engine used for the [secret component](/docs/administration/server/components/secret/) for the server.

The configuration is optional and should be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `false`.
{{% /alert %}}

## VELA_SECRET_VAULT_ADDR

This should be a fully qualified URL to the HashiCorp Vault instance.

The configuration is optional and should be provided as a `string`.

## VELA_SECRET_VAULT_AUTH_METHOD

This should be the authentication method to obtain a token from the HashiCorp Vault instance used for the [secret component](/docs/administration/server/components/secret/) for the server.

The configuration is optional and should be provided as a `string`.

## VELA_SECRET_VAULT_AWS_ROLE

This should be the HashiCorp Vault role to connect to the `auth/aws/login` endpoint used for the [secret component](/docs/administration/server/components/secret/) for the server.

The configuration is optional and should be provided as a `string`.

## VELA_SECRET_VAULT_PREFIX

This should be the prefix for k/v secrets in the HashiCorp Vault instance used for the [secret component](/docs/administration/server/components/secret/) for the server.

The configuration is optional and should be provided as a `string`.

## VELA_SECRET_VAULT_RENEWAL

This should be the frequency to renew the token for the HashiCorp Vault instance used for the [secret component](/docs/administration/server/components/secret/) for the server.

The configuration is optional and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `30m`.
{{% /alert %}}

## VELA_SECRET_VAULT_TOKEN

This should be the token for accessing the HashiCorp Vault instance used for the [secret component](/docs/administration/server/components/secret/) for the server.

The configuration is optional and should be provided as a `string`.

## VELA_SECRET_VAULT_VERSION

This should be the version for the k/v backend for the HashiCorp Vault instance used for the [secret component](/docs/administration/server/components/secret/) for the server.

The configuration is optional and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `2`.
{{% /alert %}}

## VELA_WEBUI_ADDR

This should be a fully qualified URL to the Vela [UI](/docs/administration/ui/) address.

The configuration is optional and should be provided as a `string`.

## VELA_WEBUI_OAUTH_CALLBACK_PATH

This should be the OAuth callback path for the Vela [UI](/docs/administration/ui/).

The configuration is optional and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `/account/authenticate`.
{{% /alert %}}

## VELA_WORKER_ACTIVE_INTERVAL

This should be the interval of time the workers will show as active for the [/metrics endpoint](TODO).

The configuration is optional and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `5m`.
{{% /alert %}}