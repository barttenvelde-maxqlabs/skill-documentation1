# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains custom Claude Code skills. Skills are markdown instruction files in `.claude/skills/` that Claude Code executes as slash commands.

## Available Skills

- `/btvdocumentation` — Analyzes a codebase and generates a self-contained `documentation.html` file covering architecture, modules, data flow, APIs, and configuration. Outputs clean HTML with sidebar navigation and inline CSS.

## Repository Structure

```
.claude/skills/       # Skill definition files (markdown)
```

## Skill Authoring Conventions

- Each skill is a single `.md` file in `.claude/skills/`
- Skills must declare `User-invocable: yes` and a `Name:` to be available as slash commands
- Instructions go under an `## Instructions` heading
- Writing rules and format constraints belong in the skill file itself, not in CLAUDE.md
