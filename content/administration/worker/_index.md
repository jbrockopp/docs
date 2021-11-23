---
title: "Overview"
linkTitle: "Worker"
weight: 2
description: >
  This section contains information on the Vela worker service.
---

Known as the brawn of the Vela application, this service is responsible for managing the state of workload resources.

Additionally, it processes web requests and pulls workloads from the queue to be run.

## Components

The worker is made up of several components, responsible for specific tasks, necessary for the service to operate:

| Name       | Description                                                                                       |
| ---------- | ------------------------------------------------------------------------------------------------- |
| `executor` | manages workload resources and reports results back to the [server](/docs/administration/server/) |
| `queue`    | integrates with queue providers for pulling workloads to be ran                                   |
| `runtime`  | integrates with runtime environments for executing workloads                                      |
