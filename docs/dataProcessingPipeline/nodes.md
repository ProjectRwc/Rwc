---
title: Node
layout: default
---

**Nodes** are individual operations which operate on **inputs** and return **outputs**.

```ts
interface PipelineNode {
    inputs: {
        [name: string]: PipelineNodeInput
    },
    outputs: {
        [name: string]: PipelineNodeOutput
    }
}

interface PipelineDataOutput {
    ...
}

interface PipelineNodeInput {
    uuid: string
    type: string
}

interface PipelineNodeOutput {
    uuid: string
    connectsTo: {
        [connectionId: string]: PipelineConnection
    }
}
```