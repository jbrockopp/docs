---
title: "Source"
linkTitle: "Source"
description: >
  This section contains information on the source component for the Vela server.
---

This component is responsible for integrating with source control management (SCM) providers

## Configuration

The following options are used to configure the component:

| Name             | Environment      | Description                                       |
| ---------------- | ---------------- | ------------------------------------------------- |
| `source.driver`  | `SOURCE_DRIVER`  | type of client to control and operate source      |
| `source.url`     | `SOURCE_URL`     | full navigatable url to source system             |
| `source.client`  | `SOURCE_CLIENT`  | OAuth client ID for source system                 |
| `source.secret`  | `SOURCE_SECRET`  | OAuth client secret for source system             |
| `source.context` | `SOURCE_CONTEXT` | message to set in commit status for source system |

{{% alert color="info" %}}
All available options support `VELA_*` prefixes for the environment variables. For example:
* `SOURCE_DRIVER` - type of client to control and operate queue
* `VELA_SOURCE_DRIVER` - type of client to control and operate queue
  {{% /alert %}}

## Drivers

The following drivers are available to configure the component:

| Name     | Description                               | Documentation            |
| -------- | ----------------------------------------- | ------------------------ |
| `github` | uses a GitHub instance for source control | https://github.com/about |