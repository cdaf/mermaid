# Basic graph

::: mermaid
graph

  A-->B
  B-->C

:::

# Flowchart

::: mermaid
flowchart TD

  A[Start] --> B{Is it?};
  B -->|Yes| C[OK];
  C --> D[Rethink];
  D --> B;
  B ---->|No| E[End];
:::

# Connected Subgraphs

::: mermaid
flowchart

  subgraph one
    a1-->a2
  end

  subgraph two
    b1-->b2
  end

  one --> two
  two --> c2

:::

# Side by side (flowchart)

::: mermaid
flowchart

  subgraph Default-PreFlow
    FC-ConstructTargetUrl(FC-ConstructTargetUrl)
    KVM-Load-Microservice-URL(KVM-Load-Microservice-URL)
    JS-OverrideTargetUrl(JS-OverrideTargetUrl)
  end

  subgraph Pre-Proxy-Flow-Hook
    KVM-GetRate(KVM-GetRate)
    SpikeArrest(SpikeArrest)
  end

:::

# Side by side using Graph

::: mermaid
graph TB

  subgraph Default-PostFlow
    a-->B
  end

  subgraph Default-PreFlow
    FC-ConstructTargetUrl(FC-ConstructTargetUrl) --> KVM-Load-Microservice-URL(KVM-Load-Microservice-URL)
    KVM-Load-Microservice-URL --> JS-OverrideTargetUrl(JS-OverrideTargetUrl)
  end

  subgraph Pre-Proxy-Flow-Hook
    KVM-GetRate(KVM-GetRate) --> SpikeArrest(SpikeArrest)
  end

:::
