---
title: "Runtime"
linkTitle: "Runtime"
description: >
  This section contains information on the runtime component for the worker.
---

This component is responsible for ...

## Configuration

The following options are used to configure the component:

| Name                        | Description                                                  | Required | Default                  | Environment Variables                                           |
| --------------------------- | ------------------------------------------------------------ | -------- | ------------------------ | --------------------------------------------------------------- |
| `runtime.config`            | path to configuration file for the runtime                   | `false`  | `N/A`                    | `RUNTIME_CONFIG`<br>`VELA_RUNTIME_CONFIG`                       |
| `runtime.driver`            | type of client to control and operate runtime                | `true`   | `docker`                 | `RUNTIME_DRIVER`<br>`VELA_RUNTIME_DRIVER`                       |
| `runtime.namespace`         | namespace to use for the runtime (only for kubernetes)       | `false`  | `N/A`                    | `RUNTIME_NAMESPACE`<br>`VELA_RUNTIME_NAMESPACE`                 |
| `runtime.privileged-images` | images allowed to run in privileged mode for the runtime     | `false`  | `[ target/vela-docker ]` | `RUNTIME_PRIVILEGED_IMAGES`<br>`VELA_RUNTIME_PRIVILEGED_IMAGES` |
| `runtime.volumes`           | path to host volumes to mount into resources for the runtime | `false`  | `N/A`                    | `RUNTIME_VOLUMES`<br>`VELA_RUNTIME_VOLUMES`                     |

## Drivers

The following drivers are available to configure the component:

| Name         | Description                                                           | Documentation          |
| ------------ | --------------------------------------------------------------------- | ---------------------- |
| `docker`     | uses a Docker daemon for creating and managing runtime resources      | https://docker.io/     |
| `kubernetes` | uses a Kubernetes cluster for creating and managing runtime resources | https://kubernetes.io/ |