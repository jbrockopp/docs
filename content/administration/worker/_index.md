---
title: "Overview"
linkTitle: "Worker"
weight: 2
description: >
  This section contains information on the Vela worker service.
---

Known as the brawn of the Vela application, this service is responsible for managing the state of workload resources.

Additionally, it processes web requests and pulls workloads from the queue to be run.

// TODO: add more information

## Installation

// TODO: add something here ?

### Step 1: Download the Image

The Vela worker is provided via a [Docker image](https://docs.docker.com/get-started/#what-is-a-container-image).

You can use the [`docker pull` command](https://docs.docker.com/engine/reference/commandline/pull/) to download the image:

```shell
$ docker pull target/vela-worker:latest
```

{{% alert title="Note:" color="primary" %}}
The `latest` tag will ensure you install the most-recent version of the Vela worker.

To see the full list of available versions, please refer to [the official registry](https://hub.docker.com/r/target/vela-worker).
{{% /alert %}}

### Step 2: Start the Worker

Start the Vela worker as a [Docker container](https://docs.docker.com/get-started/overview/#containers) that is configured via environment variables.

You can use the [`docker run` command](https://docs.docker.com/engine/reference/commandline/run/) to start the worker:

```shell
docker run \
  --detach=true \
  --env=QUEUE_DRIVER=redis \
  --env=QUEUE_ADDR=redis://redis:6379 \
  --env=VELA_SERVER_ADDR=http://localhost:8080 \
  --env=VELA_SERVER_SECRET=<shared-secret> \
  --name=worker \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  target/vela-worker:latest
```

{{% alert title="Note:" color="primary" %}}
For a full list of configuration options, please see the [TODO]().
{{% /alert %}}

### Step 3: Verify the Worker Logs

Ensure the worker started up successfully and is running as expected by inspecting the logs.

You can use the [`docker logs` command](https://docs.docker.com/engine/reference/commandline/logs/) to verify the logs:

```shell
$ docker logs worker
```

## Components

The worker is made up of several components, responsible for specific tasks, necessary for the service to operate:

| Name       | Description                                                                                       |
| ---------- | ------------------------------------------------------------------------------------------------- |
| `executor` | manages workload resources and reports results back to the [server](/docs/administration/server/) |
| `queue`    | integrates with queue providers for pulling workloads to be ran                                   |
| `runtime`  | integrates with runtime environments for executing workloads                                      |
