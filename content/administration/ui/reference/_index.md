---
title: "Reference"
linkTitle: "Reference"
weight: 4
description: >
  This section contains a reference of configuration options for the Vela UI service.
---

## VELA_API

This variable sets a fully qualified URL to the Vela [server](/docs/administration/server/) address.

The variable is required and should be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable should match [the `VELA_ADDR` variable](/docs/administration/server/reference/#vela_addr) provided to the server.
{{% /alert %}}

## VELA_DOCS_URL

This variable sets a fully qualified URL to the documentation website for Vela.

The variable is optional and can be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `https://go-vela.github.io/docs/`.
{{% /alert %}}

## VELA_FEEDBACK_URL

This variable sets a fully qualified URL to the feedback website for Vela.

The variable is optional and can be provided as a `string`.

{{% alert title="Note:" color="primary" %}}
This variable has a default value of `https://github.com/go-vela/ui/issues/new/`.
{{% /alert %}}