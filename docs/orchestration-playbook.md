# AI Orchestration Playbook

This playbook shows how to structure prompts and workflows so an AI agent can reliably execute multi-step tasks.

## Core Principles

1. **Outcome first**
   - Define the final artifact and where it should live.
   - Example: "Create a markdown reference in `references/` explaining Gemini 3 image uploads."

2. **Constraints are guardrails**
   - Specify architectural rules, naming, and output folders.
   - Example: "Follow SOLID, keep outputs in `references/`, and use prompt-based filenames."

3. **Tooling is non-negotiable**
   - Instruct the agent to use the available tools, not assumptions.
   - Example: "Use the CLI web-search command to collect sources." 

4. **Short feedback loops**
   - Request changes after a checkpoint instead of in one giant prompt.
   - Example: "Make it brutalist" then "Increase asymmetry and remove polish." 

5. **Separate research from execution**
   - Gather facts first, then implement.
   - Example: "Find the best OpenAI image model, then add `image-generate`."

## Prompting Template

Use this template as a starting point:

- **Goal:** What should be produced?
- **Constraints:** Architecture, style, output locations, naming.
- **Tools:** Which commands or APIs must be used.
- **Checkpoints:** When to pause for review.
- **Success criteria:** What “done” looks like.

## Example Prompt

"Build a Node.js CLI toolkit. Use SOLID and a command registry. Add a web-search command that stores results in `references/`. After you implement, run one search and save the output."
