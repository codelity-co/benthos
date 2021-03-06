---
title: bloblang
type: input
status: deprecated
categories: ["Utility"]
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/input/bloblang.go
-->

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

:::warning DEPRECATED
This component is deprecated and will be removed in the next major version release. Please consider moving onto [alternative components](#alternatives).
:::

Generates messages at a given interval using a [Bloblang](/docs/guides/bloblang/about)
mapping executed without a context. This allows you to generate messages for
testing your pipeline configs.

```yaml
# Config fields, showing default values
input:
  bloblang:
    mapping: ""
    interval: 1s
    count: 0
```

## Alternatives

This input has been [renamed to `generate`](/docs/components/inputs/generate).


## Fields

### `mapping`

A [bloblang](/docs/guides/bloblang/about) mapping to use for generating messages.


Type: `string`  
Default: `""`  

```yaml
# Examples

mapping: root = "hello world"

mapping: root = {"test":"message","id":uuid_v4()}
```

### `interval`

The time interval at which messages should be generated, expressed either as a duration string or as a cron expression. If set to an empty string messages will be generated as fast as downstream services can process them.


Type: `string`  
Default: `"1s"`  

```yaml
# Examples

interval: 5s

interval: 1m

interval: 1h

interval: '@every 1s'

interval: 0,30 */2 * * * *

interval: 30 3-6,20-23 * * *
```

### `count`

An optional number of messages to generate, if set above 0 the specified number of messages is generated and then the input will shut down.


Type: `number`  
Default: `0`  


