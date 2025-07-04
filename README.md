# Master Context Engineering with Gemini

> Unlock the full potential of AI coding assistants. This project is an optimized adaptation of Cole Duclos's original [Context Engineering repository](https://github.com/coleam00/context-engineering-intro), meticulously reconfigured for seamless integration with the Gemini CLI. Discover a powerful workflow designed to make your AI coding truly effective.

This comprehensive template guides you through Context Engineering – the essential discipline of crafting precise context for AI coding assistants, ensuring they have every piece of information needed to deliver robust, end-to-end solutions.

> **Context Engineering is 10x better than prompt engineering and 100x better than vibe coding.**

## 🚀 Quick Start: Your Path to AI-Powered Development

Get started rapidly with this template. Follow these steps to leverage Gemini for your coding tasks:

```bash
# 1. Get the template: Clone this repository to your local machine.
git clone https://github.com/coleam00/Context-Engineering-Intro.git
cd Context-Engineering-Intro

# 2. Define your project's AI rules: Customize GEMINI.md with your specific coding standards and guidelines.
# (Optional: A robust template is already provided.)

# 3. Provide examples: Populate the 'examples/' folder with relevant code snippets. This is crucial for AI understanding.
# (Highly Recommended!)

# 4. Outline your feature: Describe your new feature's requirements in INITIAL.md.
# (This is your starting point for any new development.)

# 5. Generate a comprehensive PRP: Instruct Gemini to create a detailed Product Requirements Prompt.
# Ask Gemini to run the script:
bash scripts/generate-prp.sh INITIAL.md

# 6. Execute the PRP: Command Gemini to implement your feature based on the generated PRP.
# Ask Gemini to run the script:
bash scripts/execute-prp.sh PRPs/your-feature-name.md
```

## 📚 Table of Contents

- [What is Context Engineering?](#what-is-context-engineering)
- [The Workflow with Gemini](#the-workflow-with-gemini)
- [Template Structure](#template-structure)
- [Step-by-Step Guide](#step-by-step-guide)
- [Writing Effective INITIAL.md Files](#writing-effective-initial.md-files)
- [The PRP Workflow](#the-prp-workflow)
- [Using Examples Effectively](#using-examples-effectively)
- [Best Practices](#best-practices)

## What is Context Engineering?

Context Engineering marks a fundamental shift from traditional prompt engineering, transforming how we interact with AI coding assistants.

### Prompt Engineering vs. Context Engineering

**Prompt Engineering:**
- Relies on clever wording and specific phrasing.
- Limits the scope to how you articulate a single task.
- *Analogy: Handing someone a sticky note with brief instructions.*

**Context Engineering:**
- Establishes a holistic system for delivering comprehensive context.
- Integrates documentation, code examples, project rules, established patterns, and robust validation mechanisms.
- *Analogy: Providing a complete screenplay, detailing every scene, character, and plot point.*

### Why Context Engineering is Indispensable

1.  **Minimizes AI Failures**: Most AI agent shortcomings stem from a lack of context, not model capability. Context Engineering bridges this gap.
2.  **Guarantees Consistency**: Your AI assistant will consistently adhere to your project's established patterns and conventions.
3.  **Empowers Complex Features**: Tackle multi-step implementations with confidence, as the AI navigates intricate tasks with rich, structured context.
4.  **Fosters Self-Correction**: Integrated validation loops enable the AI to identify and rectify its own errors autonomously, leading to more reliable code.

## The Workflow with Gemini: A Two-Phase Approach

This template introduces a powerful, two-phase workflow meticulously designed to maximize Gemini's effectiveness in software development. Dive deeper into the underlying philosophy and detailed process by exploring **`WORKFLOW.md`**.

## Template Structure: Navigating Your Project

This template is organized to provide Gemini with optimal context. Here's a breakdown of the key directories and files:

```
context-engineering-intro/
├── .gemini/                  # Gemini-specific configurations and prompts
│   └── prompts/              # Core instruction sets for Gemini's operations
│       ├── generate-prp.md    # Master instructions for generating comprehensive PRPs
│       └── execute-prp.md     # Master instructions for executing PRPs and implementing features
├── PRPs/                     # Repository for Product Requirements Prompts
│   ├── templates/            # Base templates for PRP generation
│   │   └── prp_base.md       # The foundational PRP structure
│   └── EXAMPLE_multi_agent_prp.md  # A concrete example of a fully generated PRP
├── examples/                 # Your essential code examples and patterns (CRITICAL for AI learning!)
├── scripts/                  # Executable scripts to trigger Gemini's workflows
│   ├── generate-prp.sh    # Initiates the PRP generation process
│   └── execute-prp.sh     # Commands Gemini to implement a feature from a PRP
├── GEMINI.md                 # Global project rules and AI behavior guidelines for Gemini
├── INITIAL.md               # Your starting point: Define new feature requests here
├── WORKFLOW.md              # In-depth guide to the Context Engineering workflow with Gemini
└── README.md                # Project overview and quick start guide (this file)
```

## Step-by-Step Guide: Mastering the Workflow

Follow these detailed steps to effectively utilize Context Engineering with Gemini:

### 1. Define Global Rules in `GEMINI.md`

Establish your project's overarching coding standards, conventions, and AI behavior guidelines within the `GEMINI.md` file. This ensures consistent output from Gemini.

### 2. Craft Your Initial Feature Request in `INITIAL.md`

Begin by clearly articulating your desired new feature or task in `INITIAL.md`. This serves as the foundational input for Gemini's planning phase.

### 3. Generate the Comprehensive PRP

PRPs (Product Requirements Prompts) are detailed implementation blueprints. To generate a PRP, instruct Gemini to execute the dedicated script:

```bash
# Command Gemini to generate your PRP:
bash scripts/generate-prp.sh INITIAL.md
```

This command directs Gemini to consult the instructions in `.gemini/prompts/generate-prp.md`. Gemini will then analyze your `INITIAL.md` request, conduct necessary research, and produce a comprehensive PRP within the `PRPs/` directory.

### 4. Execute the PRP for Feature Implementation

Once your PRP is generated, command Gemini to implement the feature by executing the PRP:

```bash
# Command Gemini to implement your feature (replace with your PRP file name):
bash scripts/execute-prp.sh PRPs/your-feature-name.md
```

Gemini will meticulously read the specified PRP, formulate a precise implementation plan, execute each development step, and leverage integrated validation loops to self-correct any errors until all requirements are met.

## Writing Effective `INITIAL.md` Files

The `INITIAL.md` file is your primary interface for communicating new tasks to Gemini. Maximize its effectiveness by being clear and comprehensive:

*   **FEATURE**: Clearly and comprehensively describe the functionality you want to build. *Avoid vague requests like "Build a web scraper"; instead, specify "Build an async web scraper using BeautifulSoup that extracts product data from e-commerce sites, handles rate limiting, and stores results in PostgreSQL."*
*   **EXAMPLES**: Crucially, leverage the `examples/` folder. Point to specific code patterns or snippets that Gemini should mimic or reference.
*   **DOCUMENTATION**: Include links to all relevant external resources, such as API documentation, library guides, or internal server documentation.
*   **OTHER CONSIDERATIONS**: Capture any critical details, potential pitfalls, authentication requirements, rate limits, or performance considerations that Gemini should be aware of.

## The PRP Workflow: Gemini's Operational Blueprint

The Product Requirements Prompt (PRP) is central to Gemini's ability to deliver. Here's how the two primary scripts guide Gemini through the workflow:

### How `scripts/generate-prp.sh` Works

This script instructs Gemini to act as a **Software Architect**, following a structured process to create your PRP:

1.  **Research Phase**: Gemini analyzes your existing codebase for established patterns and conventions.
2.  **Documentation Gathering**: Gemini collects and integrates relevant external documentation, including API specifications and library quirks.
3.  **Blueprint Creation**: Gemini synthesizes this information into a detailed, step-by-step implementation plan, complete with integrated validation gates.

### How `scripts/execute-prp.sh` Works

This script commands Gemini to transition into the role of a **Skilled Developer**, meticulously executing the generated PRP:

1.  **Load Context**: Gemini ingests the entire PRP, understanding the comprehensive plan.
2.  **Plan Execution**: Gemini translates the PRP into a detailed, actionable task list.
3.  **Component Implementation**: Gemini proceeds to implement each required component, writing code and creating files.
4.  **Validation**: Gemini rigorously runs all specified tests and linters to ensure code quality and correctness.
5.  **Iterative Refinement**: If validation checks fail, Gemini intelligently analyzes the output, debugs, and corrects its own code, iterating until all issues are resolved.
6.  **Completion**: Gemini confirms that all requirements outlined in the PRP have been successfully met.

## Using Examples Effectively: Fueling AI Understanding

The `examples/` folder is **absolutely critical** for maximizing Gemini's performance. AI coding assistants learn and perform significantly better when provided with concrete patterns and existing code to reference.

## Best Practices for Optimal Results

Adhere to these best practices to ensure the most effective and efficient development experience with Gemini:

1.  **Be Explicit in `INITIAL.md`**: Never assume Gemini knows your preferences or project specifics. Provide clear, unambiguous requirements and constraints.
2.  **Provide Comprehensive Examples**: The more relevant and well-structured examples you provide, the higher the quality and accuracy of Gemini's implementations.
3.  **Implement Robust Validation Gates**: Ensure your PRPs include executable test commands and linting checks. Gemini will iterate until these validations pass, guaranteeing reliable code.
4.  **Leverage All Available Documentation**: Always include links to official API documentation, library guides, and any internal project documentation. This enriches Gemini's context significantly.
5.  **Customize `GEMINI.md`**: Tailor `GEMINI.md` with your project's unique conventions, coding standards, and specific AI behavior rules to maintain consistency across your codebase.

## Resources

- [Context Engineering Best Practices](https://www.philschmid.de/context-engineering)
