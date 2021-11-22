---
title: "Queue"
linkTitle: "Queue"
description: >
  This section contains information on the queue component for the Vela server.
---

This component is responsible for integrating with queue providers for pushing workloads to be run by a [worker](/docs/administration/worker/).

## Configuration

The following options are used to configure the component:

| Name            | Environment     | Description                                 |
| --------------- | --------------- | ------------------------------------------- |
| `queue.driver`  | `QUEUE_DRIVER`  | type of client to control and operate queue |
| `queue.config`  | `QUEUE_CONFIG`  | full connection string to queue             |
| `queue.cluster` | `QUEUE_CLUSTER` | configures the client for a queue cluster   |
| `queue.routes`  | `QUEUE_ROUTES`  | unique channels for publishing workloads    |

{{% alert color="info" %}}
All available options support `VELA_*` prefixes for the environment variables. For example:

- `QUEUE_DRIVER` - type of client to control and operate queue
- `VELA_QUEUE_DRIVER` - type of client to control and operate queue
  {{% /alert %}}

## Drivers

The following drivers are available to configure the component:

| Name    | Description                      | Documentation            |
| ------- | -------------------------------- | ------------------------ |
| `redis` | uses a Redis queue for workloads | https://redis.io         |