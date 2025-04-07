# Cursor Custom Instructions

A collection of custom instructions and prompt templates for Cursor, the AI-powered code editor.

## Table of Contents
- [Overview](#overview)
- [Contents](#contents)
  - [Rule Creator](#rule-creator-rule-creatormd)
  - [Cline Memory Bank](#cline-memory-bank-cline-memory-bankmd)
  - [PR Reviewer](#pr-reviewer-pr-reviewermd)
- [How to Use](#how-to-use)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository contains specialized instruction sets that enhance Cursor's AI capabilities for specific use cases. These instructions can be copied into Cursor's custom instructions to enable specialized behaviors.

## Contents

### Rule Creator (`rule-creator.md`)

A system prompt for creating Cursor rules from framework documentation.

**Purpose:**
- Creates standardized rules (.mdc files) that guide AI to follow framework best practices
- Ensures code adherence to latest framework patterns and versions
- Prevents common pitfalls and deprecated usage

**Process:**
1. Identifies frameworks and versions from project files
2. Recalls key features and best practices
3. Identifies potential pitfalls
4. Creates rules in .mdc format with appropriate settings

**Usage:**
- Copy into Cursor custom instructions or use as a prompt
- Request: "Please read the [Framework] docs and create/add rules for the current version"
- Result: Framework-specific .mdc files for the .cursor/rules/ folder

### Cline Memory Bank (`cline-memory-bank.md`)

A documentation-first approach for AI development with persistent memory.

**Purpose:**
- Creates an AI assistant (Cline) that maintains perfect documentation
- Allows continuity despite memory resets between sessions
- Enforces documentation-driven development

**Memory Bank Structure:**
- `projectbrief.md` - Core requirements and project scope
- `productContext.md` - Project purpose and UX goals
- `systemPatterns.md` - Architecture and design patterns
- `techContext.md` - Technologies and technical constraints
- `activeContext.md` - Current focus and recent changes
- `progress.md` - Current status and known issues

**Key Commands:**
- "enter plan mode" - Reads memory bank, verifies context, and plans approach
  - Example: "Help me create a new endpoint to get all users in the API. Please enter plan mode."
- "enter act mode" - Checks memory bank, updates docs, executes task
  - Example: "The plan looks good. Please enter act mode."
- "update memory bank" - Reviews and updates all memory bank files

**Original Source:**
- [Cline Memory Bank Documentation](https://docs.cline.bot/improving-your-prompting-skills/cline-memory-bank)

### PR Reviewer (`pr-reviewer.md`)

A structured approach for comprehensive pull request reviews with confidence ratings.

**Purpose:**
- Provides a systematic process for reviewing pull requests
- Incorporates confidence ratings (1-10) for each comment
- Includes reasoning behind feedback to improve clarity
- Assigns a final rating for the overall PR quality

**Review Process:**
0. Use available tools (Sequential Thinking MCP, git commands) to gather PR information
1. Understand the context and goals of the PR
2. Consider alternative approaches with pros and cons
3. Identify bugs, edge cases, and code smells
4. Conduct focused line-by-line review
5. Evaluate readability and maintainability
6. Verify testing coverage
7. Provide constructive feedback
8. Perform context-specific checks (performance, security, UI)
9. Assign a final PR rating (1-10)

**Usage:**
- Copy into Cursor custom instructions
- Add the PR (Pull request, diff or commit) as context for the AI
- Request: "Review the PR" or "Review the PR against <main-branch-name> branch"
- Result: Structured review with confidence ratings and actionable feedback

## How to Use

1. Copy the desired instruction set into Cursor's custom instructions
2. Follow the specific usage instructions for each rule file
3. For Cline Memory Bank, create the memory bank folder structure first

## Contributing

Feel free to enhance these instructions or add new ones by submitting pull requests.

## License

MIT License

Copyright (c) 2025
