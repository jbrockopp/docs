---
no_list: true
title: "Reference"
linkTitle: "Reference"
weight: 4
description: >
  This section contains a reference of configuration options for the Vela worker service.
---

## Components

The worker is made up of several components, responsible for specific tasks, necessary for the service to operate:

| Name       | Description                                                                                                                      |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `executor` | coordinates with the runtime to manage workload resources and reports results back to the [server](/docs/administration/server/) |
| `queue`    | integrates with a queue provider for pulling workloads, provided by the [server](/docs/administration/server/), that will be run |
| `runtime`  | integrates with a runtime environment for executing workload resources                                                           |

## VELA_BUILD_LIMIT

This variable sets a number to control the maximum amount of builds that are allowed to run concurrently on the worker.

**The variable is required** and should be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `1`.
{{% /alert %}}

## VELA_BUILD_TIMEOUT

This variable sets the maximum duration of time a build can run for on the worker before being terminated.

**The variable is required** and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `30m`.
{{% /alert %}}

## VELA_CHECK_IN

This variable sets the maximum duration of time a worker will wait before registering with the Vela [server](/docs/administration/server/).

**The variable is required** and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `15m`.
{{% /alert %}}

## VELA_EXECUTOR_DRIVER

This configuration variable is used by the [executor component](/docs/administration/worker/components/executor/) for the worker.

Examples using this configuration variable are provided in the above reference documentation.

This variable sets the driver to use for the executor functionality for the worker.

**The variable is required** and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `linux`.

The possible options to provide for this variable are:

* `linux`
* `local`
{{% /alert %}}

## VELA_EXECUTOR_LOG_METHOD

This configuration variable is used by the [executor component](/docs/administration/worker/components/executor/) for the worker.

This variable sets the logging method used by the worker for uploading workload logs to the Vela [server](/docs/administration/server/).

**The variable is required** and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `byte-chunks`.

The possible options to provide for this variable are:

* `byte-chunks`
* `time-chunks`
{{% /alert %}}

## VELA_QUEUE_ADDR

This configuration variable is used by the [queue component](/docs/administration/worker/components/queue/) for the worker.

Examples using this configuration variable are provided in the above reference documentation.

This variable sets a fully qualified URL to the queue instance for pulling workloads provided by the [server](/docs/administration/server/).

**The variable is required** and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_ADDR` variable](/docs/administration/server/reference/#vela_queue_addr) provided to the server.
{{% /alert %}}

## VELA_QUEUE_CLUSTER

This configuration variable is used by the [queue component](/docs/administration/worker/components/queue/) for the worker.

This variable enables the worker to connect to a queue cluster rather than a standalone instance.

**The variable is optional** and can be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_CLUSTER` variable](/docs/administration/server/reference/#vela_queue_cluster) provided to the server.
{{% /alert %}}

## VELA_QUEUE_DRIVER

This configuration variable is used by the [queue component](/docs/administration/worker/components/queue/) for the worker.

Examples using this configuration variable are provided in the above reference documentation.

This variable sets the driver to use for the queue functionality for the worker.

**The variable is required** and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_DRIVER` variable](/docs/administration/server/reference/#vela_queue_driver) provided to the server.

The possible options to provide for this variable are:

* `redis`
{{% /alert %}}

## VELA_QUEUE_POP_TIMEOUT

This configuration variable is used by the [queue component](/docs/administration/worker/components/queue/) for the worker.

This variable sets the maximum duration of time the worker will wait before timing out requests sent for pulling workloads.

**The variable is required** and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `60s`.
{{% /alert %}}

## VELA_QUEUE_ROUTES

This configuration variable is used by the [queue component](/docs/administration/worker/components/queue/) for the worker.

This variable sets the unique channels or topics to pull workloads from.

**The variable is required** and should be provided as a comma-separated `list` (i.e. `myRoute1,myRoute2`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `vela`.
{{% /alert %}}

## VELA_RUNTIME_CONFIG

This configuration variable is used by the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

Examples using this configuration variable are provided in the above reference documentation.

This variable sets a fully qualified system path to a configuration file for the worker.

**The variable is optional** and can be provided as a `string`.

## VELA_RUNTIME_DRIVER

This configuration variable is used by the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

Examples using this configuration variable are provided in the above reference documentation.

This variable sets the driver to use for the runtime functionality for the worker.

**The variable is required** and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `docker`.

The possible options to provide for this variable are:

* `docker`
* `kubernetes`
{{% /alert %}}

## VELA_RUNTIME_NAMESPACE

This configuration variable is used by the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

Examples using this configuration variable are provided in the above reference documentation.

This variable sets a namespace (for Kubernetes only) to use for runtime workloads.

**The variable is optional** and can be provided as a `string`.

## VELA_RUNTIME_PRIVILEGED_IMAGES

This configuration variable is used by the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

This variable sets the [Docker image(s)](https://docs.docker.com/get-started/overview/#images) that are allowed to have privileged access on the worker.

**The variable is optional** and can be provided as a comma-separated `list` (i.e. `myImage1,myImage2`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `target/vela-docker`.
{{% /alert %}}

## VELA_RUNTIME_VOLUMES

This configuration variable is used by the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

This variable sets the fully qualified system path(s) to file(s) on the host machine that will be mounted into workloads executed on that worker.

**The variable is optional** and can be provided as a comma-separated `list` (i.e. `myVolume1,myVolume2`).

## VELA_SERVER_ADDR

This variable sets a fully qualified URL to the Vela [server](/docs/administration/server/) address.

**The variable is required** and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_ADDR` variable](/docs/administration/server/reference/#vela_addr) provided to the server.
{{% /alert %}}

## VELA_SERVER_SECRET

This variable sets a shared secret for authenticating communication between workers and the server.

**The variable is required** and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_SECRET` variable](/docs/administration/server/reference/#vela_secret) provided to the server.
{{% /alert %}}

## VELA_SERVER_CERT

This variable sets a fully qualified system path to the TLS certificate used for HTTPS for the worker.

**The variable is optional** and can be provided as a `string`.

## VELA_SERVER_CERT_KEY

This variable sets a fully qualified system path to the TLS certificate key used for HTTPS for the worker.

**The variable is optional** and can be provided as a `string`.

## VELA_WORKER_ADDR

This variable sets a fully qualified URL to the Vela [worker](/docs/administration/worker/) address.

**The variable is required** and should be provided as a `string`.