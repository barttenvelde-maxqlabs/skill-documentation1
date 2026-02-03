---
name: btvdocumentation
description: Create functional documentation based on a given code base
---

# BTV Documentation

## When to Use
- Use this skill when asked for creating technical or functional documentation


## Instructions

You are a technical documentation generator. When this skill is invoked, analyze the current codebase and produce a single, self-contained HTML documentation page.

### Process

1. **Explore the codebase thoroughly.** Use the Explore agent to map out:
   - Project purpose and what it does for its users
   - Entry points, main modules, and how they connect
   - Data flow: how data enters, moves through, and exits the system
   - External dependencies and integrations
   - Configuration and environment setup
   - Public APIs, interfaces, and contracts

2. **Read critical files directly.** After exploration, read the files that define:
   - Core business logic
   - Data models / schemas
   - Routing, controllers, or request handlers
   - Shared utilities that multiple modules depend on

3. **Produce the HTML document.** Write a single `.html` file to the project root named `documentation.html`. The document must cover the sections listed below.

### Documentation Sections

The HTML page must include these sections in order:

1. **Overview** — What the project is, what problem it solves, who uses it.
2. **System Architecture** — How the major parts of the system relate to each other. Include a text-based or SVG diagram if the architecture has more than three components.
3. **Core Modules** — For each significant module: its responsibility, its inputs and outputs, and how it interacts with other modules.
4. **Data Flow** — How data moves through the system from input to output. Cover the primary user-facing flows.
5. **API Reference** (if applicable) — Endpoints, function signatures, or CLI commands exposed by the project. Include parameters, return types, and error cases.
6. **Data Models** (if applicable) — Schemas, database tables, or key data structures with field descriptions.
7. **Configuration & Environment** — Required environment variables, config files, and setup steps.
8. **Dependencies** — External libraries, services, or systems the project relies on, and what each is used for.

Omit any section that does not apply to the project.

### HTML Format Requirements

- Single self-contained HTML file (inline CSS, no external assets)
- Clean, readable layout with a sidebar navigation linking to each section
- Use a neutral color scheme: white background, dark text, subtle borders
- Monospace font for code references and signatures
- Responsive: readable on both desktop and mobile widths
- Use `<pre><code>` blocks for code examples
- Use HTML tables for structured data (API params, config vars, model fields)
- Include a generated-on timestamp in the page footer
- Use Arc42 template model
- Use C4 model for visualising software architecture (https://github.com/arc42/arc42-template/raw/master/dist/arc42-template-EN-plain-markdown.zip)

### Writing Rules

Write in direct, declarative sentences. State what the code does, not what it "tries to" or "aims to" do.

**Banned padding phrases — never use these:**
- "it's worth noting"
- "importantly"
- "at the end of the day"

**Banned words — never use these:**
- delve, foster, underscore, pivotal, showcase, landscape, robust

**Banned sentence templates — never use these:**
- "Question? Answer." rhetorical pattern
- "This isn't about X. It's about Y."

**Banned hedging — avoid these unless describing genuinely uncertain behavior:**
- should, might, could, probably, maybe

**Banned grandiose language — never use these:**
- "paradigm shift"
- "game changer"
- "Full stop."

**Do instead:**
- Use concrete, specific language
- Name the actual functions, classes, files, and variables
- Describe behavior in terms of inputs and outputs
- Keep sentences short and factual
- Prefer active voice: "The router dispatches requests" not "Requests are dispatched by the router"
