<!-- <p align="center">
  <img src="https://via.placeholder.com/120?text=🧭" alt="Skill Compass Logo" width="120">
</p> -->

<h1 align="center">Skill Compass</h1>

<p align="center">
  <strong>Navigate the skill universe — Stop reinventing the wheel, start discovering.</strong>
</p>

A smart skill search engine for agents — discover reusable skills and workflows instantly.

## 🌟 Why Skill Compass?

**Finding the right skill shouldn't be harder than building it yourself.**

When you need a capability, you shouldn't have to:
- Wonder if a solution already exists
- Manually browse multiple marketplaces
- Guess which skills are actually high-quality

Skill Compass searches across sources using multi-field retrieval and returns ranked recommendations with quality signals (e.g., GitHub stars), so you can quickly find the best option.

## 🛠️ How It Works

```text
1. You: "I need a skill for CI/CD automation"

2. Skill Compass:
   ├── Builds structured query from your intent
   ├── Calls search API with query fields
   ├── (Optional) Asks one clarification question if needed
   └── Returns 1-3 ranked recommendations

3. You: Select the best match
   └── Skill Compass learns from your feedback
```

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| Smart Retrieval | Jointly searches over name, description, and usage context for better relevance |
| Quality Signals | Shows relevance + GitHub stars |
| Clarification Loop | Asks one targeted question if results are ambiguous |
| Feedback Telemetry | Continuously improves ranking |

## 🚀 Installation

### Option 1: Via skill manager (Easiest)

```bash
npx skills add https://github.com/LittleDinoC/skill-compass --skill skill-compass
```

### Option 2: Manual install

You can download the specific skill folder and place it in your skills directory.

```bash
# Navigate to your skills directory (e.g., for Claude Code)
cd ~/.claude/skills 

# Extract only the specific skill folder
npx degit LittleDinoC/skill-compass/skills/skill-compass skill-compass
```

Note: This installs only the skill-compass package without cloning the entire repository history.

## 🔍 Usage

The skill activates automatically when you ask your agent to discover, find, or search for skills.

### Example Sessions

Simple search:

```
You: "Find me a skill for git commit conventions"

Skill Compass:
> Searching for skills...

Recommendations:
1. conventional-commits (github/awesome-copilot, 26.8k repo stars ⭐)
   Best for: Structured commit message generation following Conventional Commits specification.
   This skill guides you through creating standardized, descriptive commit messages with a structured XML format. It includes instructions, examples, and validation to ensure your commits follow the Conventional Commits specification.

2. git-commit (github/awesome-copilot, 26.8k repo stars ⭐)
   Best for: Complete commit workflow with intelligent staging
   A more comprehensive option that handles the full git commit workflow: auto-detecting type and scope from changes, generating conventional commit messages from diff, interactive commits with overrides, and intelligent file staging for logical grouping.
```


Search with clarification:

```
You: "I need a skill for testing"

Skill Compass:
> I found several testing skills, but they serve different purposes. What type of testing do you need?
   1. Test-Driven Development (TDD) — Write tests first, then implement code to make them pass
   2. Test Generation — Generate comprehensive tests for existing code (multi-language)
   3. Language-Specific Testing — Focused testing for specific languages (Python, C++, etc.)

You: "End-to-end testing"

Skill Compass:
> Refined search...

Recommendations:
1. e2e-testing-patterns (wshobson/agents, 32.3k repo stars ⭐)
   - Fit: Master E2E testing with Playwright and Cypress, flaky test debugging, CI/CD integration.
```

## Search Behavior

| Scenario | Behavior |
|----------|----------|
| Clear intent | Returns top recommendations immediately |
| Ambiguous results | Asks exactly one clarification question |
| No results | Prompts for refined intent |
| User verdict | Sends feedback for ranking improvement |

## ⚖️ License

Released under the Apache License 2.0.