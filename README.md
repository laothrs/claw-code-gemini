# Claw Code
## High-Performance AI-Native Development Harness

Claw Code is a professional-grade, high-performance command-line interface (CLI) and development harness implemented in safe Rust. It provides a robust environment for AI-native engineering, offering workspace-aware context management, advanced tool orchestration, and multi-provider LLM integration.

While inspired by contemporary agentic workflows, Claw Code is a clean-room implementation designed for maximum execution speed, memory safety, and extensible architecture.

---

## Google Gemini Integration

Claw Code features native, high-bandwidth integration with Google Gemini via its OpenAI-compatible interface. This allows developers to leverage the massive context windows and low-latency performance of Gemini models directly within their local development environment.

The system is optimized for:
- **Gemini 2.5 Flash**: Optimized for speed and high-frequency tool interactions.
- **Gemini 2.0 Flash**: Balanced performance for complex reasoning tasks.
- **Gemini 1.5 Pro**: High-capacity reasoning for large-scale codebase analysis.

By default, Claw Code is configured to utilize Gemini 2.5 Flash as its primary reasoning engine, ensuring an responsive and efficient agentic experience.

---

## Technical Architecture

Claw Code is built on a modular Rust workspace, ensuring professional-grade reliability and performance:

- **Core Runtime**: Manages session state, conversation compaction, and execution loops.
- **Provider Abstraction**: Unified interface for Gemini, Anthropic, OpenAI, and xAI.
- **Tool Infrastructure**: A comprehensive suite of workspace-aware tools including shell execution, file manipulation, semantic search, and web integration.
- **Plugin System**: Extensible architecture allowing for custom toolsets and specialized agent behaviors.
- **Security & Permissions**: Granular permission model for tool execution (Full Access, Partial, or Deny).

---

## Installation and Deployment

### Prerequisites

- Rust Stable Toolchain (1.75+)
- Cargo Package Manager
- Valid API credentials for chosen providers

### Global Installation

To install the Claw Code CLI globally on your system, execute the following command from the repository root:

```bash
cargo install --path rust/crates/claw-cli --locked
```

---

## Configuration

### Authentication

Claw Code utilizes environment variables for provider authentication. To enable Google Gemini support, configure your shell environment as follows:

```bash
# Required for Gemini models
export GEMINI_API_KEY="your_api_key_here"

# Optional: Override default base URL
export GEMINI_BASE_URL="https://generativelanguage.googleapis.com/v1beta/openai"
```

For alternative providers, the following variables are supported:
- **Anthropic**: `ANTHROPIC_API_KEY`
- **xAI (Grok)**: `XAI_API_KEY`
- **OpenAI**: `OPENAI_API_KEY`

### Path Persistence

Ensure that the Cargo binary directory is included in your system PATH to execute `claw` from any workspace:

```bash
export PATH="$HOME/.cargo/bin:$PATH"
```

---

## Usage

### Interactive REPL

Launch the interactive agent session within any project directory:

```bash
claw
```

### One-Shot Prompts

Execute specific tasks or queries directly from the terminal:

```bash
claw prompt "Analyze the memory management patterns in crates/runtime"
```

### Model Selection

Specify an alternative model for specific requirements:

```bash
claw prompt --model gemini-1.5-pro "Perform a deep security audit of the plugin pipeline"
```

---

## Functional Capabilities

- **Workspace Awareness**: Automatic ingestion of project-specific instructions via `CLAW.md`.
- **Advanced Tooling**: Integrated support for local shell, multi-file editing, grep/glob search, and web-based research.
- **Session Management**: Persistent session logging with the ability to pause and resume complex agentic workflows.
- **MCP Compatibility**: Designed to align with the Model Context Protocol for future-proof tool integration.

---

## Acknowledgments

This project acknowledges the foundational architectural patterns and research derived from the original Claw Code repository by [ultraworkers](https://github.com/ultraworkers/claw-code).

---

## Disclaimer

Claw Code is an independent clean-room implementation. It is not affiliated with, endorsed by, or maintained by Anthropic or any other third-party LLM provider. This software is provided for professional development and research purposes.

---

## Community and Support

Project development is driven by the technical community at instruct.kr. For further technical documentation and community engagement, visit the official community platform.
