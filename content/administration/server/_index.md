---
title: "Overview"
linkTitle: "Server"
weight: 1
description: >
  This section contains information on the Vela server service.
---

Known as the brains of the Vela application, this service is responsible for managing the state of application resources.

Additionally, it processes web requests and pushes workloads to the queue to be run on a [worker](/docs/administration/worker/).

## Components

The server is made up of several components, responsible for specific tasks, necessary for the service to operate:

| Name       | Description                                                                                                     |
| ---------- | --------------------------------------------------------------------------------------------------------------- |
| `compiler` | transforms a [pipeline](/docs/tour/) into an executable workload for the [worker](/docs/administration/worker/) |
| `database` | stores application data at rest for the system                                                                  |
| `queue`    | integrates with queue providers for pushing workloads to be run by a [worker](/docs/administration/worker/)     |
| `secret`   | stores sensitive application data at rest for the system                                                        |
| `source`   | integrates with source control management (SCM) providers                                                       |
