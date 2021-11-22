---
title: "Overview"
linkTitle: "Server"
weight: 1
description: >
  This section contains information on the Vela server service.
---

The server does stuff...

## Components

The server is made up of several components, responsible for specific tasks, necessary for the platform to operate:

| Name       | Description                                                                                                     | Documentation                                 |
| ---------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------- |
| `compiler` | transforms a [pipeline](/docs/tour/) into an executable workload for the [worker](/docs/administration/worker/) | [Link](/docs/administration/server/compiler/) |
| `database` | stores application data at rest for the system                                                                  | [Link](/docs/administration/server/database/) |
| `queue`    | integrates with queue providers for pushing workloads to be run by a [worker](/docs/administration/worker/)     | [Link](/docs/administration/server/queue/)    |
| `secret`   | stores sensitive application data at rest for the system                                                        | [Link](/docs/administration/server/secret/)   |
| `source`   | integrates with source control management (SCM) providers                                                       | [Link](/docs/administration/server/source/)   |
