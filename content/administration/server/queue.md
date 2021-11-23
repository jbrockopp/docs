---
title: "Queue"
linkTitle: "Queue"
description: >
  This section contains information on the queue component for the Vela server.
---

This component is responsible for integrating with queue providers for pushing workloads to be run by a [worker](/docs/administration/worker/).

Workloads published to the queue are managed with a [first in, first out (FIFO)](https://en.wikipedia.org/wiki/FIFO_(computing_and_electronics)) strategy.

## Configuration

The following options are used to configure the component:

| Name                | Description                                       | Required | Default    | Environment Variables                           |
| ------------------- | ------------------------------------------------- | -------- | ---------- | ----------------------------------------------- |
| `queue.addr`        | full connection string to the queue               | `true`   | `N/A`      | `QUEUE_ADDR`<br>`VELA_QUEUE_ADDR`               |
| `queue.cluster`     | configures the client for a queue cluster         | `false`  | `false`    | `QUEUE_CLUSTER`<br>`VELA_QUEUE_CLUSTER`         |
| `queue.driver`      | type of client to control and operate queue       | `true`   | `N/A`      | `QUEUE_DRIVER`<br>`VELA_QUEUE_DRIVER`           |
| `queue.pop.timeout` | timeout for requests that pop items off the queue | `true`   | `60s`      | `QUEUE_POP_TIMEOUT`<br>`VELA_QUEUE_POP_TIMEOUT` |
| `queue.routes`      | unique channels or topics for pushing workloads   | `true`   | `[ vela ]` | `QUEUE_ROUTES`<br>`VELA_QUEUE_ROUTES`           |

## Drivers

The following drivers are available to configure the component:

| Name    | Description                               | Documentation            |
| ------- | ----------------------------------------- | ------------------------ |
| `redis` | uses a Redis queue for managing workloads | https://redis.io         |