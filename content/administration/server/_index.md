---
no_list: true
title: "Server Overview"
linkTitle: "Server"
weight: 1
description: >
  This section contains information on the Vela server service.
---

Known as the brains of the Vela application, this service is responsible for managing the state of application resources.

This includes managing resources in the system (repositories, users etc.) and storing resource data in the database.

Additionally, the server responds to event-driven requests (webhooks) which creates new workloads to run on a [worker](/docs/administration/worker/).

After a workload is created, it is pushed to the queue which will be retrieved and executed by a worker.

As a workload is run by a worker, it will send requests to the server's API which stores the state of the workloads in the database.

// TODO: more information we should include?

## Deployment Guides

Vela supports several deployment strategies to enable the preferences of you and your team.

This section provides a list of comprehensive guides to install and start the server:

### Docker

From the [Docker official website](https://docker.io/):

> Docker takes away repetitive, mundane configuration tasks and is used throughout the development lifecycle for fast, easy and portable application development - desktop and cloud. Docker’s comprehensive end to end platform includes UIs, CLIs, APIs and security that are engineered to work together across the entire application delivery lifecycle.

Please refer to [our Docker deployment guide](/docs/administration/server/docker/) to get started.

### Kubernetes

From the [Kubernetes official website](https://kubernetes.io/):

> Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

Please refer to [our Kubernetes deployment guide](/docs/administration/server/kubernetes/) to get started.
