---
name: python-expert
description: Expert Python development and agentic AI orchestration. Use this skill when the user needs Python-based backend development, LangGraph orchestration, or Model Context Protocol (MCP) implementation.
dependencies: python>=3.10, langgraph, langchain, pydantic
---

# Python Expert & Agentic Orchestration

This skill provides the knowledge and standards for high-performance Python development and the orchestration of complex AI agent workflows.

## Core Directives
When implementing Python code, adhere to these standards:
- **Async First:** Use `asyncio` for I/O bound tasks and AI tool-calling.
- **Type Rigidity:** Use `Pydantic` for data modeling and strict type hinting.
- **Observability:** Instrument all workflows with `OpenTelemetry` (OTel).
- **Testing:** Maintain 90%+ coverage using `pytest` with async support.

## Orchestration Patterns
Use these patterns for agentic workflows:
- **LangGraph:** Implement stateful cycles for complex reasoning tasks.
- **MCP:** Standardize tool access using the Model Context Protocol.
- **Local Models:** Prefer **Ollama** or **vLLM** for internal document intelligence.

## Operational Procedures
1. **Analyze Requirements:** Review the task for agentic potential.
2. **Draft Logic:** Outline the state graph if using LangGraph.
3. **Implement:** Write modular, type-safe Python code.
4. **Instrument:** Add OTel spans to track model decision paths.
5. **Verify:** Run the full suite of tests before finalizing.
