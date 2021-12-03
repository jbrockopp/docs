---
title: "Runtime"
linkTitle: "Runtime"
description: >
  This section contains information on the runtime component for the worker.
---

This component is responsible for integrating with a runtime environment based off the configuration provided.

The runtime environment is used by Vela for executing workload resources and managing their lifecycle.

## Configuration

The following options are used to configure the component:

| Name                        | Description                                                  | Required | Default                  | Environment Variables                                           |
| --------------------------- | ------------------------------------------------------------ | -------- | ------------------------ | --------------------------------------------------------------- |
| `runtime.config`            | path to configuration file for the runtime                   | `false`  | `N/A`                    | `RUNTIME_CONFIG`<br>`VELA_RUNTIME_CONFIG`                       |
| `runtime.driver`            | type of client to control and operate runtime                | `true`   | `docker`                 | `RUNTIME_DRIVER`<br>`VELA_RUNTIME_DRIVER`                       |
| `runtime.namespace`         | namespace to use for the runtime (only for kubernetes)       | `false`  | `N/A`                    | `RUNTIME_NAMESPACE`<br>`VELA_RUNTIME_NAMESPACE`                 |
| `runtime.privileged-images` | images allowed to run in privileged mode for the runtime     | `false`  | `[ target/vela-docker ]` | `RUNTIME_PRIVILEGED_IMAGES`<br>`VELA_RUNTIME_PRIVILEGED_IMAGES` |
| `runtime.volumes`           | path to host volumes to mount into resources for the runtime | `false`  | `N/A`                    | `RUNTIME_VOLUMES`<br>`VELA_RUNTIME_VOLUMES`                     |

{{% alert title="Note:" color="primary" %}}
For more information on these configuration options, please see the [worker reference](/docs/administration/worker/reference/).
{{% /alert %}}

## Drivers

The following drivers are available to configure the component:

| Name         | Description                                                           | Documentation          |
| ------------ | --------------------------------------------------------------------- | ---------------------- |
| `docker`     | uses a Docker daemon for creating and managing runtime resources      | https://docker.io/     |
| `kubernetes` | uses a Kubernetes cluster for creating and managing runtime resources | https://kubernetes.io/ |

### Docker

From the [Docker official website](https://docker.io/):

> Docker takes away repetitive, mundane configuration tasks and is used throughout the development lifecycle for fast, easy and portable application development - desktop and cloud. Docker’s comprehensive end to end platform includes UIs, CLIs, APIs and security that are engineered to work together across the entire application delivery lifecycle.

The below configuration displays an example of starting the Vela worker that will use a Docker runtime:

```diff
$ docker run \
  --detach=true \
  --env=VELA_QUEUE_DRIVER=redis \
  --env=VELA_QUEUE_ADDR=redis://<password>@<hostname>:<port>/<database> \
+ --env=VELA_RUNTIME_DRIVER=docker \
  --env=VELA_SERVER_ADDR=https://vela-server.company.com \
  --env=VELA_SERVER_SECRET=<shared-secret> \
  --env=VELA_WORKER_ADDR=https://vela-worker.company.com \
  --name=worker \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  --volume=/var/run/docker.sock:/var/run/docker.sock
  target/vela-worker:latest
```

{{% alert title="Note:" color="primary" %}}
This Docker configuration is enabled by default and is not necessary to provide in order for Vela to operate.
{{% /alert %}}

### Kubernetes

From the [Kubernetes official website](https://kubernetes.io/):

> Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

The below configuration displays an example of starting the Vela worker that will use a Kubernetes runtime:

```diff
$ docker run \
  --detach=true \
  --env=VELA_QUEUE_DRIVER=redis \
  --env=VELA_QUEUE_ADDR=redis://<password>@<hostname>:<port>/<database> \
+ --env=VELA_RUNTIME_DRIVER=kubernetes \
+ --env=VELA_RUNTIME_CONFIG=/root/.kube/config \
+ --env=VELA_RUNTIME_NAMESPACE=vela \
  --env=VELA_SERVER_ADDR=https://vela-server.company.com \
  --env=VELA_SERVER_SECRET=<shared-secret> \
  --env=VELA_WORKER_ADDR=https://vela-worker.company.com \
  --name=worker \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  --volume=/var/run/docker.sock:/var/run/docker.sock \
+ --volume=/root/.kube/config:/root/.kube/config \
  target/vela-worker:latest
```