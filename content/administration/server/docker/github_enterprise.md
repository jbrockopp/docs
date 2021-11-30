---
title: "GitHub Enterprise"
linkTitle: "GitHub Enterprise"
weight: 2
description: >
  This section contains information on using GitHub Enterprise with the Vela server service.
---

## Prerequisites

This section provides all required dependencies to install and start the server with Docker that connects to GitHub Enterprise.

### Dependency 1: Docker

[Docker](https://docker.com/) will be used for downloading the server and managing the lifecycle of the application.

You can refer to [Docker's official documentation](https://docs.docker.com/get-docker/) on installing and configuring the service.

### Dependency 2: Redis

[Redis](https://redis.io/) will be used for storing workloads, created by the server, that will run on a [worker](/docs/administration/worker/).

You can refer to [Redis's official documentation](https://redis.io/topics/quickstart/) on installing and configuring the service.

// TODO: more dependencies we need to cover?

## Installation

This section provides an example of installing the server with Docker that connects to GitHub Enterprise.

This example only shows a subset of all possible configuration options.

### Step 1: Download the Image

Download the [Docker image](https://docs.docker.com/get-started/overview/#images) for the Vela server from [DockerHub](https://hub.docker.com/).

You can use the [`docker pull` command](https://docs.docker.com/engine/reference/commandline/pull/) to download the image:

```shell
$ docker pull target/vela-server:latest
```

{{% alert title="Note:" color="primary" %}}
The `latest` tag will ensure you install the most-recent version of the Vela server.

To see the full list of available versions, please refer to [the official registry](https://hub.docker.com/r/target/vela-server).
{{% /alert %}}

### Step 2: Create an Encryption Key

Create an [Advanced Encryption Standard (AES)](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) key used for encrypting sensitive data at rest in the database.

You can use the [`openssl` command](https://www.openssl.org/) to generate the AES key:

```shell
$ openssl aes-128-cbc -k secret -P -md sha1
```

{{% alert title="Note:" color="primary" %}}
This command will output multiple key/value pairs for the AES key.

The specific value we need from the output is the line with `key` in it (i.e. `key=<value>`).
{{% /alert %}}

### Step 3: Create a Shared Secret

Create a shared secret used for authenticating communication between workers and the server.

You can use the [`openssl` command](https://www.openssl.org/) to generate the shared secret:

```shell
$ openssl rand -hex 16
```

### Step 4: Create an OAuth Application

Create a [GitHub Enterprise OAuth application](https://docs.github.com/enterprise-server@3.3/developers/apps/building-oauth-apps/creating-an-oauth-app) used for authentication and authorization with GitHub.

![OAuth Application](/docs/administration/server/github_enterprise_oauth.png)

{{% alert title="Warning:" color="secondary" %}}
The `Homepage URL` should match the `VELA_ADDR` environment variable below.

The `Authorization callback URL` should match `<VELA_ADDR>/authenticate` from the environment variable below.
{{% /alert %}}

### Step 5: Start the Server

Start the Vela server as a [Docker container](https://docs.docker.com/get-started/overview/#containers) that is configured via environment variables.

You can use the [`docker run` command](https://docs.docker.com/engine/reference/commandline/run/) to start the server:

```shell
$ docker run \
  --detach=true \
  --env=VELA_ADDR=https://vela.company.com \
  --env=VELA_DATABASE_ENCRYPTION_KEY=<encryption-key> \
  --env=VELA_QUEUE_DRIVER=redis \
  --env=VELA_QUEUE_ADDR=redis://<password>@<hostname>:<port>/<database> \
  --env=VELA_PORT=443 \
  --env=VELA_SECRET=<shared-secret> \
  --env=VELA_SCM_ADDR=https://git.company.com \
  --env=VELA_SCM_CLIENT=<oauth-client-id> \
  --env=VELA_SCM_SECRET=<oauth-client-secret> \
  --name=server \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  target/vela-server:latest
```

{{% alert title="Note:" color="primary" %}}
For a full list of configuration options, please see the [server reference](/docs/administration/server/reference/).
{{% /alert %}}

### Step 6: Verify the Server Logs

Ensure the server started up successfully and is running as expected by viewing the logs.

You can use the [`docker logs` command](https://docs.docker.com/engine/reference/commandline/logs/) to inspect the logs:

```shell
$ docker logs server
```

### Step 7: Install Workers

After the server is up and running, you need to install workers to run workloads.

Please refer to [the worker installation docs](/docs/administration/worker/) for more information.