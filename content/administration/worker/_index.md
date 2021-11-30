---
no_list: true
title: "Overview"
linkTitle: "Worker"
weight: 2
description: >
  This section contains information on the Vela worker service.
---

Known as the brawn of the Vela application, this service is responsible for managing the state of workload resources.

This includes pulling workloads, provided by the [server](/docs/administration/server/), from the queue to be run.

When a workload is fetched from the queue, the worker will create and delete resources through the lifecycle of the workload.

During this time, the worker will send API requests to the server to report the status and progress of these resources.

Additionally, the worker has its own API for processing web requests.

// TODO: more information we should include?

## Deployment Guides

Vela supports several deployment strategies to enable the preferences of you and your team.

This section provides a list of comprehensive guides to install and start the worker:

### Docker

From the [Docker official website](https://docker.io/):

> Docker takes away repetitive, mundane configuration tasks and is used throughout the development lifecycle for fast, easy and portable application development - desktop and cloud. Docker’s comprehensive end to end platform includes UIs, CLIs, APIs and security that are engineered to work together across the entire application delivery lifecycle.

Please refer to [our Docker deployment guide](/docs/administration/worker/docker/) to get started.

### Kubernetes

From the [Kubernetes official website](https://kubernetes.io/):

> Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

Please refer to [our Kubernetes deployment guide](/docs/administration/worker/kubernetes/) to get started.
