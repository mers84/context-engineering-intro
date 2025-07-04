# Context Engineering Template for Gemini

> This project is an adaptation of the original [Context Engineering repository](https://github.com/coleam00/context-engineering-intro) by Cole Duclos, reconfigured and optimized for use with Gemini. Context engineering is the way to make AI coding assistants actually work, and this template provides the workflow to achieve that.

A comprehensive template for getting started with Context Engineering - the discipline of engineering context for AI coding assistants so they have the information necessary to get the job done end-to-end.

> **Context Engineering is 10x better than prompt engineering and 100x better than vibe coding.**

## 🚀 Quick Start

```bash
# 1. Clone this template
git clone https://github.com/coleam00/Context-Engineering-Intro.git
cd Context-Engineering-Intro

# 2. Set up your project rules (optional - template provided)
# Edit GEMINI.md to add your project-specific guidelines

# 3. Add examples (highly recommended)
# Place relevant code examples in the examples/ folder

# 4. Create your initial feature request
# Edit INITIAL.md with your feature requirements

# 5. Generate a comprehensive PRP (Product Requirements Prompt)
# Ask Gemini to run the script:
bash scripts/generate-prp.sh INITIAL.md

# 6. Execute the PRP to implement your feature
# Ask Gemini to run the script:
bash scripts/execute-prp.sh PRPs/your-feature-name.md
```

## 📚 Table of Contents

- [What is Context Engineering?](#what-is-context-engineering)
- [The Workflow with Gemini](#the-workflow-with-gemini)
- [Template Structure](#template-structure)
- [Step-by-Step Guide](#step-by-step-guide)
- [Writing Effective INITIAL.md Files](#writing-effective-initialmd-files)
- [The PRP Workflow](#the-prp-workflow)
- [Using Examples Effectively](#using-examples-effectively)
- [Best Practices](#best-practices)

## What is Context Engineering?

Context Engineering represents a paradigm shift from traditional prompt engineering:

### Prompt Engineering vs Context Engineering

**Prompt Engineering:**
- Focuses on clever wording and specific phrasing
- Limited to how you phrase a task
- Like giving someone a sticky note

**Context Engineering:**
- A complete system for providing comprehensive context
- Includes documentation, examples, rules, patterns, and validation
- Like writing a full screenplay with all the details

### Why Context Engineering Matters

1.  **Reduces AI Failures**: Most agent failures aren't model failures - they're context failures.
2.  **Ensures Consistency**: The AI follows your project patterns and conventions.
3.  **Enables Complex Features**: The AI can handle multi-step implementations with proper context.
4.  **Self-Correcting**: Validation loops allow the AI to fix its own mistakes.

## The Workflow with Gemini

This project uses a two-phase workflow designed to maximize Gemini's effectiveness. For a detailed explanation of the philosophy and process, please read **`WORKFLOW.md`**.

## Template Structure

```
context-engineering-intro/
├── .gemini/
│   └── prompts/
│       ├── generate-prp.md    # Instructions for generating PRPs
│       └── execute-prp.md     # Instructions for executing PRPs
├── PRPs/
│   ├── templates/
│   │   └── prp_base.md       # Base template for PRPs
│   └── EXAMPLE_multi_agent_prp.md  # Example of a complete PRP
├── examples/                  # Your code examples (critical!)
├── scripts/
│   ├── generate-prp.sh    # Script to invoke PRP generation
│   └── execute-prp.sh     # Script to invoke PRP execution
├── GEMINI.md                 # Global rules for the Gemini assistant
├── INITIAL.md               # Template for feature requests
├── WORKFLOW.md              # Detailed explanation of the workflow
└── README.md                # This file
```

## Step-by-Step Guide

### 1. Set Up Global Rules (GEMINI.md)

The `GEMINI.md` file contains project-wide rules that the AI assistant will follow.

### 2. Create Your Initial Feature Request

Edit `INITIAL.md` to describe what you want to build.

### 3. Generate the PRP

PRPs (Product Requirements Prompts) are comprehensive implementation blueprints. To generate one, ask Gemini to run the corresponding script:

```bash
# Ask Gemini to run:
bash scripts/generate-prp.sh INITIAL.md
```

This command instructs Gemini to follow the instructions in `.gemini/prompts/generate-prp.md` to read your request, conduct research, and create a detailed PRP in the `PRPs/` directory.

### 4. Execute the PRP

Once generated, execute the PRP to implement your feature:

```bash
# Ask Gemini to run (replace the file name):
bash scripts/execute-prp.sh PRPs/your-feature-name.md
```

The AI assistant will read the PRP, create a detailed implementation plan, execute each step with validation, and use the validation loops to correct any errors until everything works.

## Writing Effective INITIAL.md Files

**FEATURE**: Be specific and comprehensive.
**EXAMPLES**: Leverage the `examples/` folder.
**DOCUMENTATION**: Include all relevant resources.
**OTHER CONSIDERATIONS**: Capture important details.

## The PRP Workflow

### How `scripts/generate-prp.sh` Works

The script tells Gemini to follow a process:
1.  **Research Phase**: Analyzes your codebase for patterns.
2.  **Documentation Gathering**: Gathers relevant API docs.
3.  **Blueprint Creation**: Creates a step-by-step implementation plan with validation gates.

### How `scripts/execute-prp.sh` Works

1.  **Load Context**: Reads the entire PRP.
2.  **Plan**: Creates a detailed task list.
3.  **Execute**: Implements each component.
4.  **Validate**: Runs tests and linters.
5.  **Iterate**: Fixes any issues found.
6.  **Complete**: Ensures all requirements are met.

## Using Examples Effectively

The `examples/` folder is **critical** for success. AI coding assistants perform much better when they can see patterns to follow.

## Best Practices

1.  **Be Explicit in INITIAL.md**: Don't assume the AI knows your preferences.
2.  **Provide Comprehensive Examples**: More examples = better implementations.
3.  **Use Validation Gates**: PRPs should include test commands that must pass.
4.  **Leverage Documentation**: Include official API docs.
5.  **Customize GEMINI.md**: Add your conventions and rules.

## Resources

- [Context Engineering Best Practices](https://www.philschmid.de/context-engineering)
