---
title: "SCM"
linkTitle: "SCM"
description: >
  This section contains information on the scm component for the Vela server.
---

This component is responsible for integrating with a source control management (SCM) system based off the configuration provided.

The SCM system is used by Vela for both authentication and authorization of interactions performed within the application.

## Configuration

The following options are used to configure the component:

| Name               | Description                                                     | Required | Default                                                  | Environment Variables                         |
| ------------------ | --------------------------------------------------------------- | -------- | -------------------------------------------------------- | --------------------------------------------- |
| `scm.addr`         | fully qualified url for the SCM                                 | `true`   | `https://github.com`                                     | `SCM_ADDR`<br>`VELA_SCM_ADDR`                 |
| `scm.client`       | client ID from the generated OAuth application on the SCM       | `true`   | `N/A`                                                    | `SCM_CLIENT`<br>`VELA_SCM_CLIENT`             |
| `scm.context`      | message to set in commit status on the SCM                      | `true`   | `continuous-integration/vela`                            | `SCM_CONTEXT`<br>`VELA_SCM_CONTEXT`           |
| `scm.driver`       | type of client to control and operate SCM                       | `true`   | `github`                                                 | `SCM_DRIVER`<br>`VELA_SCM_DRIVER`             |
| `scm.scopes`       | permission scopes to apply for the OAuth credentials on the SCM | `true`   | `[ repo, repo:status, user:email, read:user, read:org ]` | `SCM_SCOPES`<br>`VELA_SCM_SCOPES`             |
| `scm.secret`       | client secret from the generated OAuth application on the SCM   | `true`   | `N/A`                                                    | `SCM_SECRET`<br>`VELA_SCM_SECRET`             |
| `scm.webhook.addr` | url for webhooks on the SCM to send requests to                 | `false`  | the address of the Vela server                           | `SCM_WEBHOOK_ADDR`<br>`VELA_SCM_WEBHOOK_ADDR` |

{{% alert title="Note:" color="primary" %}}
For more information on these configuration options, please see the [server reference](/docs/administration/server/reference/).
{{% /alert %}}

## Drivers

The following drivers are available to configure the component:

| Name     | Description                                             | Documentation             |
| -------- | ------------------------------------------------------- | ------------------------- |
| `github` | uses a GitHub or GitHug Enterprise instance for the SCM | https://github.com/about/ |

### GitHub

From the [GitHub official website](https://github.com/about/):

> GitHub is where the world builds software. Millions of developers and companies build, ship, and maintain their software on GitHub—the largest and most advanced development platform in the world.

The below configuration displays an example of starting the Vela server that will connect to a GitHub SCM:

```diff
$ docker run \
  --detach=true \
  --env=VELA_ADDR=https://vela.company.com \
  --env=VELA_DATABASE_ENCRYPTION_KEY=<encryption-key> \
  --env=VELA_QUEUE_DRIVER=redis \
  --env=VELA_QUEUE_ADDR=redis://<password>@<hostname>:<port>/<database> \
  --env=VELA_PORT=443 \
  --env=VELA_SECRET=<shared-secret> \
+ --env=VELA_SCM_DRIVER=github
+ --env=VELA_SCM_ADDR=https://github.com
  --env=VELA_SCM_CLIENT=<oauth-client-id> \
  --env=VELA_SCM_SECRET=<oauth-client-secret> \
  --name=server \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  target/vela-server:latest
```

{{% alert title="Note:" color="primary" %}}
This GitHub configuration is enabled by default and is not necessary to provide in order for Vela to operate.
{{% /alert %}}

### GitHub Enterprise

From the [GitHub Enterprise official website](https://github.com/enterprise):

> GitHub Enterprise helps you work seamlessly across your organization on a platform designed for collaboration. Embrace innersource, iterate faster, and ship more frequently using best practices from open source teams.

The below configuration displays an example of starting the Vela server that will connect to a GitHub Enterprise SCM:

```diff
$ docker run \
  --detach=true \
  --env=VELA_ADDR=https://vela.company.com \
  --env=VELA_DATABASE_ENCRYPTION_KEY=<encryption-key> \
  --env=VELA_QUEUE_DRIVER=redis \
  --env=VELA_QUEUE_ADDR=redis://<password>@<hostname>:<port>/<database> \
  --env=VELA_PORT=443 \
  --env=VELA_SECRET=<shared-secret> \
+ --env=VELA_SCM_DRIVER=github \
+ --env=VELA_SCM_ADDR=https://git.company.com \
  --env=VELA_SCM_CLIENT=<oauth-client-id> \
  --env=VELA_SCM_SECRET=<oauth-client-secret> \
  --name=server \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  target/vela-server:latest
```