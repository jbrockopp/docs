---
title: "Reference"
linkTitle: "Reference"
weight: 2
description: >
  This section contains a reference of the configuration options for the Vela worker service.
---

## VELA_BUILD_LIMIT

This should be a number that controls the maximum amount of builds that are allowed to run concurrently for the worker.

The configuration is required and should be provided as an `integer`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `1`.
{{% /alert %}}

## VELA_BUILD_TIMEOUT

This should be a duration of time that controls the maximum amount of time a build can run for on the worker.

The configuration is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `30m`.
{{% /alert %}}

## VELA_CHECK_IN

This should be a duration of time that controls when the worker will connect and check in with the Vela [server](/docs/administration/server/).

The configuration is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `15m`.
{{% /alert %}}

## VELA_EXECUTOR_DRIVER

This should be the driver used for the [executor component](/docs/administration/worker/components/executor/) for the worker.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `linux`.

The possible options to provide for this variable are:

* `linux`
* `local`
{{% /alert %}}

## VELA_EXECUTOR_LOG_METHOD

This should be the logging method or strategy used for the [executor component](/docs/administration/worker/components/executor/) for the worker.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `linux`.

The possible options to provide for this variable are:

* `byte-chunks`
* `time-chunks`
{{% /alert %}}

## VELA_QUEUE_ADDR

This should be a fully qualified URL to the queue system used for the [queue component](/docs/administration/worker/components/queue/) for the worker.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_ADDR` variable](/docs/administration/server/reference/#vela_queue_addr) provided to the server.
{{% /alert %}}

## VELA_QUEUE_CLUSTER

This should enable the [queue component](/docs/administration/worker/components/queue/) for the worker to connect to a cluster rather than a standalone instance.

The configuration is optional and should be provided as a `boolean`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_CLUSTER` variable](/docs/administration/server/reference/#vela_queue_cluster) provided to the server.
{{% /alert %}}

## VELA_QUEUE_DRIVER

This should be the driver used for the [queue component](/docs/administration/worker/components/queue/) for the worker.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_QUEUE_DRIVER` variable](/docs/administration/server/reference/#vela_queue_driver) provided to the server.

The possible options to provide for this variable are:

* `redis`
{{% /alert %}}

## VELA_QUEUE_POP_TIMEOUT

This should be the timeout for requests sent for pulling workloads used for the [queue component](/docs/administration/worker/components/queue/) for the worker.

The configuration is required and should be provided as a `duration` (i.e. `5s`, `10m`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `60s`.
{{% /alert %}}

## VELA_QUEUE_ROUTES

This should be the unique channels or topics for pulling workloads used for the [queue component](/docs/administration/worker/components/queue/) for the worker.

The configuration is required and should be provided as a comma-separated list (i.e. `myRoute1,myRoute2`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `vela`.
{{% /alert %}}

## VELA_RUNTIME_CONFIG

This should be the path to a configuration file for the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

The configuration is optional and should be provided as a `string`.

## VELA_RUNTIME_DRIVER

This should be the driver used for the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `docker`.

The possible options to provide for this variable are:

* `docker`
* `kubernetes`
{{% /alert %}}

## VELA_RUNTIME_NAMESPACE

This should be the namespace to use for the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

The configuration is optional and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable is used for the Kubernetes runtime only.
{{% /alert %}}

## VELA_RUNTIME_PRIVILEGED_IMAGES

This should be the [Docker image(s)](https://docs.docker.com/get-started/overview/#images) that are allowed to have privileged access on the worker to use for the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

The configuration is optional and should be provided as a comma-separated list (i.e. `myImage1,myImage2`).

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `target/vela-docker`.

The possible options to provide for this variable are:

* any Docker image accessible by the worker
{{% /alert %}}

## VELA_RUNTIME_VOLUMES

This should be the path(s) to files on the host the worker is running on to use for the [runtime component](/docs/administration/worker/components/runtime/) for the worker.

The configuration is optional and should be provided as a comma-separated list (i.e. `myVolume1,myVolume2`).

{{% alert title="Note:" color="primary" %}}
The possible options to provide for this variable are:

* any valid path to a file on the host that will be mounted into every container
{{% /alert %}}

## VELA_SERVER_ADDR

This should be a fully qualified URL to the Vela [server](/docs/administration/server/) address.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_ADDR` variable](/docs/administration/server/reference/#vela_addr) provided to the server.
{{% /alert %}}

## VELA_SERVER_SECRET

This should be a shared secret with the Vela [server](/docs/administration/server/) for authenticating communication between workers and the server.

The configuration is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_SECRET` variable](/docs/administration/server/reference/#vela_secret) provided to the server.
{{% /alert %}}

## VELA_SERVER_CERT

This should be the path to the TLS certificate used for HTTPS for the worker.

The configuration is optional and should be provided as a `string`.

## VELA_SERVER_CERT_KEY

This should be the path to the TLS certificate key used for HTTPS for the worker.

The configuration is optional and should be provided as a `string`.

## VELA_WORKER_ADDR

This should be a fully qualified URL to the Vela [worker](/docs/administration/worker/) address.

The configuration is required and should be provided as a `string`.