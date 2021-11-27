---
title: "Executor"
linkTitle: "Executor"
description: >
  This section contains information on the executor component for the worker.
---

This component is responsible for coordinating with [the runtime](/docs/administration/worker/runtime/) to manage workload resources.

Throughout the lifecycle of these resources, this component will track and report results back to the [server](/docs/administration/server/).

## Configuration

The following options are used to configure the component:

| Name                  | Description                                       | Required | Default       | Environment Variables                               |
| --------------------- | ------------------------------------------------- | -------- | ------------- | --------------------------------------------------- |
| `executor.driver`     | type of client to control and operate executor    | `true`   | `linux`       | `EXECUTOR_DRIVER`<br>`VELA_EXECUTOR_DRIVER`         |
| `executor.log_method` | method used to publish logs back to the server    | `true`   | `byte-chunks` | `EXECUTOR_LOG_METHOD`<br>`VELA_EXECUTOR_LOG_METHOD` |

## Drivers

The following drivers are available to configure the component:

| Name    | Description                                            | Documentation          |
| ------- | ------------------------------------------------------ | ---------------------- |
| `linux` | uses a Linux executor for running workloads            | https://www.linux.org/ |
| `local` | uses a Local executor for running workloads (CLI only) | `N/A`                  |