## The "Hook" (YAML Frontmatter)

The frontmatter is the most critical part because it’s how the agent decides to "load" the skill.

Be Verbose in Description: Use keywords the agent is likely to encounter in your prompts (e.g., "LangGraph," "asyncio," "refactor").

Set Scope: Explicitly state what the skill is not for to prevent "skill creep."

YAML
---
name: python-agent-architect
description: Use for designing stateful multi-agent systems, LangGraph nodes, and Python-based tool-calling logic.
dependencies: python>=3.10, langgraph
---

## The "Prime Directive" (Core Principles)

Establish 3–5 non-negotiable rules. This prevents the AI from defaulting to generic, "lazy" code.

Example: "Always use Pydantic models for function arguments."

Example: "Never use time.sleep(); always use await asyncio.sleep()."

## Structural Standards (The "How")

Define the specific architecture you want. If you have a preferred way of organizing directories or naming variables, put it here.

File Structure: "Place all nodes in /nodes and all state schemas in state.py."

Logging: "Every function must include an OTel span with the task_id attribute."

## Operational Procedures (The Workflow)

Give the agent a step-by-step "algorithm" for completing a task. This ensures consistency across different sessions.

Context Check: Search the existing codebase for similar patterns.

Schema First: Define the data types before writing logic.

Draft & Lint: Write code and immediately run ruff or flake8.

Test: Generate a pytest file before considering the task "done."

## Error Handling & Edge Cases

Tell the agent how to fail gracefully.

Retry Logic: "If an LLM call fails, use an exponential backoff decorator."

Validation: "If a tool returns an empty list, do not proceed; ask the user for clarification."

Summary Checklist for a Great SKILL.md

Feature	Best Practice	Why?
Name	Kebab-case (e.g., fastapi-expert)	Standard CLI compatibility.
Description	Start with "Use this when..."	Helps the router model match intent.
Language	Use imperative verbs ("Do," "Always," "Ensure")	Commands are followed better than suggestions.
Context	Reference local tools (Ollama, vLLM)	Ensures the AI stays within your environment.
Examples	Include a small code snippet of the "ideal" state	Provides a "one-shot" learning example.
Pro Tip: The "Anti-Skill"

Consider adding a section called "Avoid These Patterns". For example, if you hate print() debugging and want only logging, explicitly ban print(). This is often more effective than simply asking for logging.
