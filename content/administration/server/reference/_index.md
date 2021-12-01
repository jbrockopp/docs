---
no_list: true
title: "Reference"
linkTitle: "Reference"
weight: 4
description: >
  This section contains a reference of configuration options for the Vela server service.
---

## Components

The server is made up of several components, responsible for specific tasks, necessary for the service to operate:

| Name       | Description                                                                                                         |
| ---------- | ------------------------------------------------------------------------------------------------------------------- |
| `compiler` | transforms a [pipeline](/docs/tour/) into an executable workload for the [worker](/docs/administration/worker/)     |
| `database` | integrates with a database provider for storing application data at rest                                            |
| `queue`    | integrates with a queue provider for pushing workloads that will be run by a [worker](/docs/administration/worker/) |
| `secret`   | integrates with a secret provider for storing sensitive application data at rest                                    |
| `source`   | integrates with a source control management (SCM) provider for authentication and authorization                     |

## VELA_ACCESS_TOKEN_DURATION

This variable sets the maximum duration of time a Vela access token for a user is valid on the server.

The access token is used for authenticating user's requests to the server.

The variable is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `15m`.
{{% /alert %}}

## VELA_ADDR

This variable sets a fully qualified URL to the Vela [server](/docs/administration/server/) address.

The variable is required and should be provided as a `string`.

## VELA_COMPILER_GITHUB

This configuration variable is used by the [compiler component](/docs/administration/server/components/compiler/) for the server.

This variable enables using a GitHub Enterprise Server as a registry for fetching pipeline [templates](/docs/tour/templates/) from.

The variable is optional and can be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `false`.
{{% /alert %}}

## VELA_COMPILER_GITHUB_TOKEN

This configuration variable is used by the [compiler component](/docs/administration/server/components/compiler/) for the server.

This variable sets a [Personal Access Token (PAT)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) for fetching pipeline [templates](/docs/tour/templates/) from the GitHub Enterprise Server.

The variable is optional and can be provided as a `string`.

## VELA_COMPILER_GITHUB_URL

This configuration variable is used by the [compiler component](/docs/administration/server/components/compiler/) for the server.

This variable sets a fully qualified URL to the GitHub Enterprise Server used for fetching pipeline [templates](/docs/tour/templates/) from.

The variable is optional and can be provided as a `string`.

## VELA_DATABASE_ADDR

This configuration variable is used by the [database component](/docs/administration/server/components/database/) for the server.

This variable sets a fully qualified URL to the database instance for storing data at rest.

The variable is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `vela.sqlite`.
{{% /alert %}}

## VELA_DATABASE_COMPRESSION_LEVEL

This configuration variable is used by the [database component](/docs/administration/server/components/database/) for the server.

This variable sets the level of compression for workload logs, uploaded by the Vela [worker](/docs/administration/worker/), which are stored in the database.

The variable is required and should be provided as an `integer`.

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

This configuration variable is used by the [database component](/docs/administration/server/components/database/) for the server.

This variable sets the maximum number of [idle connections](https://pkg.go.dev/database/sql#DB.SetMaxIdleConns) allowed for the database client.

The variable is required and should be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `2`.
{{% /alert %}}

## VELA_DATABASE_CONNECTION_LIFE

This configuration variable is used by the [database component](/docs/administration/server/components/database/) for the server.

This variable sets the maximum duration of time [a connection is reusable](https://pkg.go.dev/database/sql#DB.SetConnMaxLifetime) for the database client.

The variable is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `30m`.
{{% /alert %}}

## VELA_DATABASE_CONNECTION_OPEN

This configuration variable is used by the [database component](/docs/administration/server/components/database/) for the server.

This variable sets the maximum number of [open connections](https://pkg.go.dev/database/sql#DB.SetMaxOpenConns) allowed for the database client.

The variable is required and should be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `0` (meaning no limit is set).
{{% /alert %}}

## VELA_DATABASE_DRIVER

This configuration variable is used by the [database component](/docs/administration/server/components/database/) for the server.

This variable sets the driver to use for the database functionality for the server.

The variable is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `sqlite3`.

The possible options to provide for this variable are:

* `postgres`
* `sqlite3`
  {{% /alert %}}

## VELA_DATABASE_ENCRYPTION_KEY

This configuration variable is used by the [database component](/docs/administration/server/components/database/) for the server.

This variable sets the AES key for encrypting/decrypting values for data stored in the database.

The variable is required and should be provided as an `string`.

## VELA_DATABASE_SKIP_CREATION

This configuration variable is used by the [database component](/docs/administration/server/components/database/) for the server.

This variable enables skipping the creation of tables and indexes in the database system.

The variable is optional and can be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `false`.
{{% /alert %}}

## VELA_DEFAULT_BUILD_TIMEOUT

This variable sets the default maximum duration of time a build is allowed to run on a worker.

The variable is optional and can be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `0`.
{{% /alert %}}

## VELA_DISABLE_WEBHOOK_VALIDATION

This variable disables validation of webhooks sent by the SCM to the server.

The variable is optional and can be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable should only be used for local development.

This variable has a default value of `false`.
{{% /alert %}}

## VELA_ENABLE_SECURE_COOKIE

This enables using cookies with the secure flag set by the server.

The variable is optional and should be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable should only be used for local development.

This variable has a default value of `true`.
{{% /alert %}}

## VELA_MODIFICATION_ADDR

This configuration variable is used by the [compiler component](/docs/administration/server/components/compiler/) for the server.

This variable sets a fully qualified URL to the modification endpoint used for the compiler.

The variable is optional and can be provided as a `string`.

## VELA_MODIFICATION_RETRIES

This configuration variable is used by the [compiler component](/docs/administration/server/components/compiler/) for the server.

This variable sets the maximum number of times to resend failed requests to the modification endpoint for the compiler.

The variable is optional and can be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `5`.
{{% /alert %}}

## VELA_MODIFICATION_SECRET

This configuration variable is used by the [compiler component](/docs/administration/server/components/compiler/) for the server.

This variable sets a shared secret for authenticating communication between the compiler and the modification endpoint.

The variable is optional and can be provided as a `string`.

## VELA_MODIFICATION_TIMEOUT

This configuration variable is used by the [compiler component](/docs/administration/server/components/compiler/) for the server.

This variable sets the maximum duration of time the compiler will wait before timing out requests sent to the modification endpoint.

The variable is optional and can be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `8s`.
{{% /alert %}}

## VELA_PORT

This variable sets the port the server API responds on for HTTP requests.

The variable is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `8080`.
{{% /alert %}}

## VELA_QUEUE_ADDR

This configuration variable is used by the [queue component](/docs/administration/server/components/queue/) for the server.

This variable sets a fully qualified URL to the queue instance for pushing workloads that will be run by a [worker](/docs/administration/worker/).

The variable is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_ADDR` variable](/docs/administration/worker/reference/#vela_queue_addr) provided to the worker.
{{% /alert %}}

## VELA_QUEUE_CLUSTER

This configuration variable is used by the [queue component](/docs/administration/server/components/queue/) for the server.

This variable enables the server to connect to a queue cluster rather than a standalone instance.

The variable is optional and can be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_CLUSTER` variable](/docs/administration/worker/reference/#vela_queue_cluster) provided to the worker.
{{% /alert %}}

## VELA_QUEUE_DRIVER

This configuration variable is used by the [queue component](/docs/administration/server/components/queue/) for the server.

This variable sets the driver to use for the queue functionality for the server.

The variable is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_DRIVER` variable](/docs/administration/worker/reference/#vela_queue_driver) provided to the worker.

The possible options to provide for this variable are:

* `redis`
  {{% /alert %}}

## VELA_QUEUE_POP_TIMEOUT

This configuration variable is unused by the [queue component](/docs/administration/server/components/queue/) for the server.

This variable sets the maximum duration of time the worker will wait before timing out requests sent for pushing workloads.

The variable is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `60s`.
{{% /alert %}}

## VELA_QUEUE_ROUTES

This configuration variable is used by the [queue component](/docs/administration/server/components/queue/) for the server.

This variable sets the unique channels or topics to push workloads to.

The variable is required and should be provided as a comma-separated `list` (i.e. `myRoute1,myRoute2`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `vela`.
{{% /alert %}}

## VELA_REFRESH_TOKEN_DURATION

This variable sets the maximum duration of time a Vela refresh token for a user is valid on the server.

The refresh token is used for refreshing a user's access token on the server.

The variable is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `8h`.
{{% /alert %}}

## VELA_REPO_ALLOWLIST

This variable sets a group of repositories, from the SCM, that can be enabled on the server.

The configuration is optional and can be provided as a comma-separated `list` (i.e. `myRoute1,myRoute2`).

## VELA_SCM_ADDR

This configuration variable is used by the [SCM component](/docs/administration/server/components/scm/) for the server.

This variable sets a fully qualified URL to the source control management (SCM) system.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `https://github.com`.
{{% /alert %}}

## VELA_SCM_CLIENT

This configuration variable is used by the [SCM component](/docs/administration/server/components/scm/) for the server.

This variable sets the client ID from the OAuth application created on the SCM system.

The variable is required and should be provided as a `string`.

## VELA_SCM_CONTEXT

This configuration variable is used by the [SCM component](/docs/administration/server/components/scm/) for the server.

This variable sets the message to set in the commit status on the SCM system.

The variable is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `continuous-integration/vela`.
{{% /alert %}}

## VELA_SCM_DRIVER

This configuration variable is used by the [SCM component](/docs/administration/server/components/scm/) for the server.

This variable sets the driver to use for the SCM functionality for the server.

The variable is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `github`.

The possible options to provide for this variable are:

* `github`
  {{% /alert %}}

## VELA_SCM_SCOPES

This configuration variable is used by the [SCM component](/docs/administration/server/components/scm/) for the server.

This variable sets the permission scopes to apply for OAuth credentials captured from the SCM system.

The variable is required and should be provided as a comma-separated `list` (i.e. `myScope1,myScope2`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `read:org,read:user,repo,repo:status,user:email`.
{{% /alert %}}

## VELA_SCM_SECRET

This configuration variable is used by the [SCM component](/docs/administration/server/components/scm/) for the server.

This variable sets the client secret from the OAuth application created on the SCM system.

The variable is required and should be provided as a `string`.

## VELA_SCM_WEBHOOK_ADDR

This configuration variable is used by the [SCM component](/docs/administration/server/components/scm/) for the server.

This variable sets a fully qualified URL on the SCM system to send webhooks to the server.

The variable is optional and can be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of [the `VELA_ADDR` variable](/docs/administration/server/reference/#vela_addr) provided to the server.
{{% /alert %}}

## VELA_SECRET

This variable sets a shared secret with the Vela [worker](/docs/administration/worker/) for authenticating communication between workers and the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_SERVER_SECRET` variable](/docs/administration/worker/reference/#vela_server_secret) provided to the worker.
{{% /alert %}}

## VELA_SECRET_VAULT

This configuration variable is used by the [secret component](/docs/administration/server/components/secret/) for the server.

This variable enables using HashiCorp Vault as a secret engine.

The variable is optional and can be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `false`.
{{% /alert %}}

## VELA_SECRET_VAULT_ADDR

This configuration variable is used by the [secret component](/docs/administration/server/components/secret/) for the server.

This variable sets a fully qualified URL to the HashiCorp Vault instance.

The variable is optional and can be provided as a `string`.

## VELA_SECRET_VAULT_AUTH_METHOD

This configuration variable is used by the [secret component](/docs/administration/server/components/secret/) for the server.

This variable sets the authentication method to obtain a token from the HashiCorp Vault instance.

The variable is optional and can be provided as a `string`.

## VELA_SECRET_VAULT_AWS_ROLE

This configuration variable is used by the [secret component](/docs/administration/server/components/secret/) for the server.

This variable sets the HashiCorp Vault role to connect to the `auth/aws/login` endpoint.

The variable is optional and can be provided as a `string`.

## VELA_SECRET_VAULT_PREFIX

This configuration variable is used by the [secret component](/docs/administration/server/components/secret/) for the server.

This variable sets the prefix for k/v secrets in the HashiCorp Vault instance.

The variable is optional and can be provided as a `string`.

## VELA_SECRET_VAULT_RENEWAL

This configuration variable is used by the [secret component](/docs/administration/server/components/secret/) for the server.

This variable sets the frequency to renew the token for the HashiCorp Vault instance.

The variable is optional and can be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `30m`.
{{% /alert %}}

## VELA_SECRET_VAULT_TOKEN

This configuration variable is used by the [secret component](/docs/administration/server/components/secret/) for the server.

This variable sets the token for accessing the HashiCorp Vault instance.

The variable is optional and can be provided as a `string`.

## VELA_SECRET_VAULT_VERSION

This configuration variable is used by the [secret component](/docs/administration/server/components/secret/) for the server.

This variable sets the version for the k/v backend for the HashiCorp Vault instance.

The variable is optional and can be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `2`.
{{% /alert %}}

## VELA_WEBUI_ADDR

This variable sets a fully qualified URL to the Vela [UI](/docs/administration/ui/) address.

The variable is optional and can be provided as a `string`.

## VELA_WEBUI_OAUTH_CALLBACK_PATH

This variable sets the endpoint to use for the OAuth callback path for the Vela [UI](/docs/administration/ui/).

The variable is optional and can be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `/account/authenticate`.
{{% /alert %}}

## VELA_WORKER_ACTIVE_INTERVAL

This variable sets the interval of time the workers will show as active for the [/metrics endpoint](TODO).

The variable is optional and can be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `5m`.
{{% /alert %}}
