---
title: "GitHub Enterprise"
linkTitle: "GitHub Enterprise"
weight: 2
description: >
  This section contains information on using GitHub Enterprise with the Vela server service.
---

## Prerequisites

This section provides all required dependencies to install and start the server with Kubernetes that connects to GitHub Enterprise.

### Dependency 1: Kubernetes

[Kubernetes](https://kubernetes.io/) will be used for downloading the server and managing the lifecycle of the application.

You can refer to [Kubernetes' official documentation](https://kubernetes.io/docs/setup/) on installing and configuring the service.

### Dependency 2: Redis

[Redis](https://redis.io/) will be used for storing workloads, created by the server, that will run on a [worker](/docs/administration/worker/).

You can refer to [Redis's official documentation](https://redis.io/topics/quickstart/) on installing and configuring the service.

// TODO: more dependencies we need to cover?

## Installation

This section provides an example of installing the server with Kubernetes that connects to GitHub Enterprise.

This example only shows a subset of all possible configuration options.

### Step 1: TODO

TODO