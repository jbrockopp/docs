---
title: "Overview"
linkTitle: "UI"
weight: 3
description: >
  This section contains information on the Vela UI service.
---

This service is responsible for providing a practically designed method for performing operations within Vela that feel intuitive.

// TODO: add more information

## Prerequisites

This section provides all required dependencies to install and start the UI.

### Dependency 1: Docker

[Docker](https://docs.docker.com/) will be used for downloading the UI and managing the lifecycle of the application.

You can refer to [Docker's official documentation](https://docs.docker.com/get-docker/) on installing and configuring the service.

// TODO: more dependencies we need to cover?

## Installation

This section provides an example on installing the UI with a subset of possible configuration options.

### Step 1: Download the Image

Download the [Docker image](https://docs.docker.com/get-started/overview/#images) for the Vela UI from [DockerHub](https://hub.docker.com/).

You can use the [`docker pull` command](https://docs.docker.com/engine/reference/commandline/pull/) to download the image:

```shell
$ docker pull target/vela-ui:latest
```

{{% alert title="Note:" color="primary" %}}
The `latest` tag will ensure you install the most-recent version of the Vela server.

To see the full list of available versions, please refer to [the official registry](https://hub.docker.com/r/target/vela-server).
{{% /alert %}}

### Step 2: Start the UI

Start the Vela UI as a [Docker container](https://docs.docker.com/get-started/overview/#containers) that is configured via environment variables.

You can use the [`docker run` command](https://docs.docker.com/engine/reference/commandline/run/) to start the worker:

```shell
$ docker run \
  --detach=true \
  --env=VELA_API=https://vela.company.com \
  --name=ui \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  target/vela-ui:latest
```

{{% alert title="Note:" color="primary" %}}
For a full list of configuration options, please see the [TODO]().
{{% /alert %}}

### Step 3: Verify the UI Logs

Ensure the UI started up successfully and is running as expected by inspecting the logs.

You can use the [`docker logs` command](https://docs.docker.com/engine/reference/commandline/logs/) to verify the logs:

```shell
$ docker logs ui
```
