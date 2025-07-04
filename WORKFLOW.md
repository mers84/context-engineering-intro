# Context Engineering Workflow with Gemini

This document explains the workflow and philosophy behind this project, adapted for use with the Gemini AI assistant. The system is designed to maximize the assistant's effectiveness by minimizing errors and hallucinations through structured context preparation.

## The Philosophy: Sharpening the Axe

The methodology is inspired by Abraham Lincoln's quote: *"Give me six hours to chop down a tree, and I will spend the first four sharpening the axe."*

In our case:
- **The Tree**: Is the software feature we want to build.
- **Sharpening the Axe**: Is the process of **Context Engineering**. Instead of asking Gemini to code something directly ("vibe coding"), we first collaborate with it to create an exhaustive, error-proof implementation plan.

This process is divided into two clear, sequential phases.

---

## Phase 1: Plan Generation (Create the PRP)

In this phase, we act as software architects. Our goal is not to write code, but to produce a **Product Requirements Prompt (PRP)**: a requirements document and technical attack plan designed specifically for Gemini to execute.

### How It Works:

1.  **Your Input (`INITIAL.md`)**:
    - You start by editing the `INITIAL.md` file.
    - Here, you describe the desired functionality, provide links to relevant documentation, point to code examples in the `examples/` directory, and mention any important considerations or "gotchas."

2.  **The Invocation (Generate the PRP)**:
    - You ask Gemini to start the plan generation flow by executing a shell script. This script acts as an alias or a marker for a complex task.
    - **Command:**
      ```bash
      # Ask Gemini to run:
      bash scripts/generate-prp.sh INITIAL.md
      ```

3.  **Gemini's Process**:
    - Upon receiving this instruction, Gemini doesn't just read the script. It interprets that it must follow the detailed instructions in `.gemini/prompts/generate-prp.md`.
    - Gemini will analyze your `INITIAL.md`, research the code examples, consult external documentation if necessary, and use the `PRPs/templates/prp_base.md` template to structure its output.

4.  **The Output (The "Sharpened Axe")**:
    - Gemini will write a new `.md` file to the `PRPs/` directory.
    - This file is the **PRP**. It contains:
        - A detailed description of the goal.
        - The file architecture to be created.
        - Data models and pseudocode.
        - **Crucially**: A `Validation Loop` with commands (`pytest`, `ruff`, `mypy`) that Gemini will later use to self-validate its own code.

---

## Phase 2: Plan Execution (Implement the PRP)

With the PRP ready, the planning phase is over. Now, the task is purely execution. We switch Gemini's role from "architect" to "builder."

### How It Works:

1.  **Your Input (The PRP)**:
    - The input for this phase is the path to the PRP file generated in the previous phase.

2.  **The Invocation (Execute the PRP)**:
    - You ask Gemini to implement the plan contained in the PRP.
    - **Command:**
      ```bash
      # Ask Gemini to run (replace the file name):
      bash scripts/execute-prp.sh PRPs/your-feature-name.md
      ```

3.  **Gemini's Process**:
    - Gemini now follows the instructions from the `gemini/prompts/execute-prp.md` prompt.
    - It will read the specified PRP, create a detailed task list (create files, write code, etc.), and begin the implementation.
    - **Self-Correction Loop**: After writing the code, Gemini will execute the commands from the PRP's `Validation Loop`. If a test fails or the linter finds an error, Gemini will use that output to debug and correct the code, repeating the process until all validations pass.

4.  **The Output (The "Chopped-Down Tree")**:
    - At the end of the process, you will have a functional, tested codebase that follows the project's conventions, all implemented autonomously by Gemini.

---

## Key Project Files

- **`GEMINI.md`**: Global rules and conventions that Gemini must follow at all times.
- **`INITIAL.md`**: Your starting point. Here you describe what you want to build.
- **`WORKFLOW.md`**: This file, explaining the process.
- **`scripts/`**: Contains the marker scripts (`generate-prp.sh`, `execute-prp.sh`) that you use to invoke the workflows.
- **`.gemini/prompts/`**: Contains the "sheet music" or master instructions that Gemini follows for each flow.
- **`PRPs/`**: Where the generated Product Requirements Prompts are stored.
- **`examples/`**: A place to put code examples that Gemini can use as a reference.
