---
layout: default
title: Sandbox
---


## Mermaid Sequenzdiagramme

[Syntax-Dokumentation](http://knsv.github.io/mermaid/#sequence-diagrams)

<div class="mermaid">
sequenceDiagram
  A-->B: tue was
  B->>C: mehr
</div>

## Mermaid Ablaufdiagramm

[Syntax-Dokumentation](http://knsv.github.io/mermaid/#flowcharts-basic-syntax)

Top-Down

<div class="mermaid">
graph TD
  A-->|text|B
  B-.text.->C
</div>

Links-Rechts

<div class="mermaid">
graph LR
  A-->|text|B
  B-. text .->C
</div>
