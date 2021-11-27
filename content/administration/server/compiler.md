---
title: "Compiler"
linkTitle: "Compiler"
description: >
  This section contains information on the compiler component for the Vela server.
---

This component is responsible for transforming a [pipeline](/docs/tour/) into an executable representation for the [worker](/docs/administration/worker/).

// TODO: add more information

## Configuration

The following options are used to configure the component:

| Name            | Description                                                              | Required | Default | Environment Variables                                   |
| --------------- | ------------------------------------------------------------------------ | -------- | ------- | ------------------------------------------------------- |
| `github-driver` | enables using a GitHub Enterprise instance as a registry for templates   | `false`  | `false` | `COMPILER_GITHUB`<br>`VELA_COMPILER_GITHUB`             |
| `github-url`    | fully qualified url to GitHub Enterprise instance for fetching templates | `false`  | `N/A`   | `COMPILER_GITHUB_URL`<br>`VELA_COMPILER_GITHUB_URL`     |
| `github-token`  | token used for authentication when fetching registry templates           | `false`  | `N/A`   | `COMPILER_GITHUB_TOKEN`<br>`VELA_COMPILER_GITHUB_TOKEN` |

## Drivers

The following drivers are available to configure the component:

| Name     | Description                                              | Documentation            |
| -------- | -------------------------------------------------------- | ------------------------ |
| `github` | uses a GitHug Enterprise instance as a template registry | https://github.com/about |