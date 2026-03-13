# HubSpot MCP Visualizer

A Claude Code skill that generates interactive dependency graphs of HubSpot MCP tools with animated reasoning traces.

## Demo

https://github.com/user-attachments/assets/mcp-visualizer.mp4

> *The visualization is rendered as an interactive widget inside Claude Code — select a prompt to trace how Claude reasons through each tool step by step.*

## What it does

When you ask Claude to visualize your HubSpot MCP tools, this skill:

1. **Discovers tools** — inspects the HubSpot MCP tools connected in your session
2. **Maps dependencies** — determines data-flow relationships between tools (e.g., search returns IDs that get-by-ID consumes)
3. **Renders an interactive graph** — displays tools as color-coded nodes organized by function (auth, read, write, schema, feedback) with animated edges showing data flow
4. **Traces reasoning** — shows step-by-step how Claude would orchestrate tools to answer a given HubSpot question

## Usage

Install the skill in Claude Code, then try any of these:

```
Visualize my HubSpot MCP tools
```

```
Trace the tool calls for "show my open deals"
```

```
Show me how Claude would answer "create a contact for John Doe"
```

You can also provide your own HubSpot question — the skill will render the visualization with a reasoning trace AND answer the question.

## How it works

- **No hardcoded tools** — the graph is built dynamically from whatever HubSpot MCP tools are connected
- **Auto-layout** — tools are placed on a tier × column grid based on their role (auth → discovery → detail → mutation)
- **Auto-routing** — edges between tools are routed automatically (straight, L-shaped, or far-right channel) to avoid overlap
- **Demo prompts** — 4 built-in traces that exercise different parts of the graph, plus support for custom user prompts

## Installation

Add the skill file to Claude Code:

```bash
claude install-skill hubspot-mcp-visualizer.skill
```

Requires a connected HubSpot account via MCP. If HubSpot tools aren't available, the skill will prompt you to connect first.
