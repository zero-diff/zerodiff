---
title: Pelican Rides a Bicycle
date: 2025-12-15
tags:
  - software
  - gen/ai
  - llm
---

# Pelican Rides a Bicycle

Below are two SVG solutions to the Simon Willison's [benchmark](https://github.com/simonw/pelican-bicycle/blob/main/README.md): `"Generate an SVG of a pelican riding a bicycle."`

### Claude Sonnet 3.5:

![claude-3-5-sonnet-20240620.svg](claude-3-5-sonnet-20240620.svg)

### Claude-Code:

![pelican-bicycle.svg](pelican-bicycle.svg)


### What Changed?!

As agentic gen/ai exploded in 2025, it felt like Willison's benchmark became a solvable problem *if we used these new agentic powers:* skills, sub-agents, tool-use and more. Using Claude-Code, I built a pipeline that now solves this problem.

The Github repo [github.com/0x6a77/pelican-rides-a-bicycle](https://github.com/0x6a77/pelican-rides-a-bicycle) let's you replicate this work and see an example of Claude-Code skills with tool-calling.

<!-- more -->

## How It Works

The Claude-Code skills pipeline orchestrates specialized capabilities:

- Agentic/AI Orchestrates the pipeline
- Image Generation: Flux diffusion model generates a bitmap of the prompt
- Vector Tracing: autotrace converts the bitmap to SVG paths

The agent's job is to know which tool to use when. This is fundamentally different from asking a transformer to generate SVG vectors from scratch.

### 2026, The Year of Agentic Pipelines?

Some might argue this doesn't solve Willison's benchmark - it solves the problem his benchmark reveals. It shows transformers can't do one-shot compositional spatial reasoning. My pipeline shows that agentic gen/ai doesn't need to because it can orchestrate specialized tools instead. The pelican benchmark is valuable for tracking raw model capabilities, but to build systems that work today, we need orchestration.[^1]

[^1]: (Stephen Wolfram's work on computational irreducibility suggests the pelican task may require a level of spatial reasoning that transformers can't do, so tool orchestration isn't just pragmatic, but potentially necessary. I plan to write about this in a future post.)

The right way forward with gen/ai is to embrace agentic gen/ai in 2026 in deeper and more interesting ways. Stay tuned for an expansion of this idea.
