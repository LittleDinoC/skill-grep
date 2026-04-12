<h1 align="center">Skill Grep</h1>

<p align="center">
  <strong>Navigate the skill universe — Stop reinventing the wheel, start discovering.</strong>
</p>

A smart skill search engine for agents — discover reusable skills and workflows instantly.

🌐 Try the Web Version: [skills.megatechai.com](https://skills.megatechai.com/). Search skills directly in your browser!

## 🌟 Why Skill Grep?

**Finding the right skill shouldn't be harder than building it yourself.**

When you need a capability, you shouldn't have to:
- Wonder if a solution already exists
- Manually browse multiple marketplaces
- Guess which skills are actually high-quality

Skill Grep searches across sources using multi-field retrieval and returns ranked recommendations with quality signals (e.g., GitHub stars), so you can quickly find the best option.

## 🛠️ How It Works

```text
1. You: "I need a skill for CI/CD automation"

2. Skill Grep:
   ├── Builds structured query from your intent
   ├── Calls search API with query fields
   ├── (Optional) Asks one clarification question if needed
   └── Returns 1-3 ranked recommendations

3. You: Select the best match
   └── Skill Grep learns from your feedback
```

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| Smart Retrieval | Jointly searches over name, description, and usage context for better relevance |
| Quality Signals | Shows relevance + GitHub stars |
| Clarification Loop | Asks one targeted question if results are ambiguous |
| Feedback Telemetry | Continuously improves ranking |

## 🚀 Installation

### For Claude Code

You can register this repository as a Claude Code Plugin marketplace by running the following command in Claude Code:

```bash
/plugin marketplace add LittleDinoC/skill-grep
```

```bash
/plugin install skill-grep@skill-grep
```

### Option 1: Via skill manager

```bash
npx skills add https://github.com/LittleDinoC/skill-grep --skill skill-grep
```

### Option 2: Manual install

You can download the specific skill folder and place it in your skills directory.

```bash
# Navigate to your skills directory (e.g., for OpenClaw)
cd ~/.openclaw/skills 

# Extract only the specific skill folder
npx degit LittleDinoC/skill-grep/skills/skill-grep skill-grep
```

Note: This installs only the skill-grep package without cloning the entire repository history.

## 🔍 Usage

The skill activates automatically when you ask your agent to discover, find, or search for skills.

### Example Sessions

Simple search:

```
You: "Find me a skill for git commit conventions"

Skill Grep:
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

Skill Grep:
> I found several testing skills, but they serve different purposes. What type of testing do you need?
   1. Test-Driven Development (TDD) — Write tests first, then implement code to make them pass
   2. Test Generation — Generate comprehensive tests for existing code (multi-language)
   3. Language-Specific Testing — Focused testing for specific languages (Python, C++, etc.)

You: "End-to-end testing"

Skill Grep:
> Refined search...

Recommendations:
1. e2e-testing-patterns (wshobson/agents, 32.3k repo stars ⭐)
   - Fit: Master E2E testing with Playwright and Cypress, flaky test debugging, CI/CD integration.
```

## 🎯 Search Behavior

| Scenario | Behavior |
|----------|----------|
| Clear intent | Returns top recommendations immediately |
| Ambiguous results | Asks exactly one clarification question |
| No results | Prompts for refined intent |
| User verdict | Sends feedback for ranking improvement |

## 📚 Research & Citation

Skill Grep is the practical extension of our paper [Multi-Field Tool Retrieval](https://arxiv.org/abs/2602.05366). While the paper proposes a framework for retrieving tools across multiple metadata fields, this project brings those insights into a functional search engine for AI agents.

If you find this work helpful for your research or projects, please cite our paper:

```text
@misc{tang2026multifieldtoolretrieval,
   title={Multi-Field Tool Retrieval}, 
   author={Yichen Tang and Weihang Su and Yiqun Liu and Qingyao Ai},
   year={2026},
   eprint={2602.05366},
   archivePrefix={arXiv},
   primaryClass={cs.IR},
   url={https://arxiv.org/abs/2602.05366}, 
}
```

## ⚖️ License

Released under the Apache License 2.0.

## 📋 User Agreement

By using Skill Grep, you agree to our [User Agreement](USER_AGREEMENT.md).

Data Collection Notice: We collect search interaction data (without involving personal privacy information) to construct public research datasets. This helps advance research in skill retrieval and agent capabilities. See the [User Agreement](USER_AGREEMENT.md) for full details.