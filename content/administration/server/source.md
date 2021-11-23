---
title: "Source"
linkTitle: "Source"
description: >
  This section contains information on the source component for the Vela server.
---

This component is responsible for integrating with source control management (SCM) providers.

## Configuration

The following options are used to configure the component:

| Name                  | Description                                                     | Required | Default                                                  | Environment Variables                               |
| --------------------- | --------------------------------------------------------------- | -------- | -------------------------------------------------------- | --------------------------------------------------- |
| `source.addr`         | fully qualified url for the SCM                                 | `true`   | `https://github.com`                                     | `SOURCE_ADDR`<br>`VELA_SOURCE_ADDR`                 |
| `source.client`       | client ID from the generated OAuth application on the SCM       | `true`   | `N/A`                                                    | `SOURCE_CLIENT`<br>`VELA_SOURCE_CLIENT`             |
| `source.context`      | message to set in commit status on the SCM                      | `true`   | `continuous-integration/vela`                            | `SOURCE_CONTEXT`<br>`VELA_SOURCE_CONTEXT`           |
| `source.driver`       | type of client to control and operate SCM                       | `true`   | `github`                                                 | `SOURCE_DRIVER`<br>`VELA_SOURCE_DRIVER`             |
| `source.scopes`       | permission scopes to apply for the OAuth credentials on the SCM | `true`   | `[ repo, repo:status, user:email, read:user, read:org ]` | `SOURCE_SCOPES`<br>`VELA_SOURCE_SCOPES`             |
| `source.secret`       | client secret from the generated OAuth application on the SCM   | `true`   | `N/A`                                                    | `SOURCE_SECRET`<br>`VELA_SOURCE_SECRET`             |
| `source.webhook.addr` | url for webhooks on the SCM to send requests to                 | `false`  | `N/A`                                                    | `SOURCE_WEBHOOK_ADDR`<br>`VELA_SOURCE_WEBHOOK_ADDR` |

## Drivers

The following drivers are available to configure the component:

| Name     | Description                                             | Documentation            |
| -------- | ------------------------------------------------------- | ------------------------ |
| `github` | uses a GitHub or GitHug Enterprise instance for the SCM | https://github.com/about |