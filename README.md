# CLI AI Toolkit

A SOLID-friendly Node.js CLI for AI utilities. It provides repeatable commands
for research, model feedback, and image generation, with outputs saved in a
predictable structure.

This repo is also a teaching lab for AI orchestration: breaking work into clear goals, giving the agent tools and constraints, and iterating with feedback.

## What This Toolkit Does

- **Web research:** Run web search and save results in `references/`.
- **Model feedback:** Send prompts/media to Gemini and save outputs in `references/aI_feedback/`.
- **Image generation:** Generate images and save them in `images/` with prompt-based names.

## The Automation Mindset

Each time you catch yourself doing a repetitive task (searching, screenshotting, generating images, summarizing), design a tool and a process that automates it. The goal is to remove yourself from the loop by turning manual steps into repeatable commands.

Live site: https://kaw393939.github.io/agentic_orchestration_toolkit/

## What Is AI Orchestration?

AI orchestration is the practice of directing an AI system through a sequence of tasks, tools, and constraints so it produces reliable, repeatable outcomes. You are not just asking for answers. You are managing a workflow.

**Metaphor for students:**
You are the CEO of a complex organization (imagine Ford Motor Company). You are not building every part yourself. You are coordinating specialists (AI models) who are experts in different fields. Your job is to define the strategy, set quality standards, and make sure the outputs fit the context. Think of yourself as both a sommelier (taste and selection) and a barista (process and consistency) to get the best final result.

## Why These Techniques Work

- **Clarity reduces error:** Specific goals and constraints reduce ambiguity.
- **Tooling increases reliability:** Explicit tool usage lowers hallucination risk.
- **Short feedback loops increase quality:** Iteration finds flaws early.
- **Organization scales reuse:** Consistent outputs become assets.
- **Separation of research and execution reduces mistakes:** Facts first, changes second.

## Start Here (Students Build from Scratch)

You will rebuild this toolkit yourself. The finished project is a reference, not a shortcut.

1. Read the playbook and quick reference.
2. Follow the build walkthrough step-by-step.
3. Run each command you create and log results.

## Setup

1. Install dependencies:

   npm install

2. Ensure your `.env` file includes:

   OPENAI_API_KEY=your_key_here
   GEMINI_API_KEY=your_key_here

### What Is a `.env` File?

A `.env` file stores environment variables (secrets and configuration) outside your code. This prevents API keys from being hard-coded into source files.

**Why it matters:**
- Keeps secrets out of Git.
- Lets you switch keys per machine or team.
- Matches common industry practice.

### Get Your API Keys

- OpenAI API key: https://platform.openai.com/api-keys
- Google Gemini API key (AI Studio): https://aistudio.google.com/app/apikey

## Usage (After You Build It)

- Dev mode:

  npm run dev -- web-search "latest AI news"

- Gemini prompt (optional files):

  npm run dev -- gemini "Summarize this image" --file ./path/to/image.jpg

- Generate an image:

  npm run dev -- image-generate "A cinematic lighthouse in a storm" --size 1024x1024

- Build and run:

  npm run build
  node dist/index.js web-search "latest AI news"

## Output Locations

- Web search output: `references/`
- Gemini responses: `references/aI_feedback/`
- Generated images: `images/`

## From-Scratch Checklist (No Skipping)

- Read the playbook and quick reference.
- Create the CLI structure and command registry.
- Add `web-search`, then dogfood it.
- Add `gemini`, then dogfood it with an image.
- Add `image-generate`, then dogfood it.
- Document outputs and paths.

## Common Failure Modes

- Missing `OPENAI_API_KEY` or `GEMINI_API_KEY` in `.env`.
- Running commands before `npm install`.
- Forgetting to save outputs in `references/` or `images/`.
- Skipping dogfooding and missing errors until later.

## Capstone Task

Add a new command from scratch and prove it works:

1. Create a new command class.
2. Register it in `src/index.ts`.
3. Run it with real input.
4. Save output to an organized folder.
5. Write a short reflection on what broke and how you fixed it.

## AI Orchestration Strategies (with Examples)

### 1. Frame the goal and constraints

**Strategy:** State the target outcome, non-negotiables, and output format.

**Example:**
"Build a Node.js CLI toolkit using SOLID, make it easy to add commands, and store research in `references/`."

### 2. Use tool-first instructions

**Strategy:** Tell the agent to use the tools it has, not to improvise.

**Example:**
"Use the CLI web-search tool to research Gemini 3 and save the results to `references/`."

### 3. Iterate with small checkpoints

**Strategy:** Ask for a first version, inspect it, then refine.

**Example:**
"Make the site brutalist." -> review -> "Push it further, more raw and asymmetrical."

### 4. Keep outputs organized

**Strategy:** Define folders and naming conventions so outputs are reusable.

**Example:**
"Save Gemini responses in `references/aI_feedback/` and name images based on the prompt."

### 5. Separate research from execution

**Strategy:** First gather info, then implement changes.

**Example:**
"Research the best OpenAI image model, then add a CLI command for image generation."

### 6. Dogfood before you commit human time

**Strategy:** Make the agent use the tool it just built, then fix issues immediately.

**Example:**
"Run the CLI web search now and keep debugging until it works perfectly."

**Dogfood Checklist:**
- Run the new command with a real input.
- Confirm files are saved in the correct folder.
- Read the output to verify formatting and completeness.
- Fix errors, rerun, and repeat until clean.

### 7. Use expert-lens reviews

**Strategy:** Request a critique using a specific expert lens (not roleplay), so feedback is anchored to a known framework or philosophy.

**Example:**
"Review this UI using brutalist principles associated with early brutalism." or "Audit this architecture using Uncle Bob style SOLID concerns."

### 8. Adversarial review (red-team your output)

**Strategy:** Ask for a failure-focused critique that tries to break assumptions.

**Example:**
"List the top 5 ways this CLI could fail in real use and how to harden it."

### 9. Constraint inversion

**Strategy:** Flip a constraint to expose tradeoffs and hidden dependencies.

**Example:**
"Assume the CLI must work offline. What must change?"

### 10. Artifact-first prompting

**Strategy:** Specify the exact artifacts to create before asking for implementation details.

**Example:**
"Create three docs: a playbook, a build walkthrough, and an image workflow guide."

## Learning Path (Suggested Order)

1. Read the playbook and quick reference.
2. Follow the build walkthrough.
3. Run the image workflow and log iterations.

## Student Walkthroughs

- [AI orchestration playbook](docs/orchestration-playbook.md)
- [Orchestration toolkit quick reference](docs/orchestration-toolkit.md)
- [Toolkit build walkthrough](docs/toolkit-build-walkthrough.md)
- [Image generation workflow](docs/image-generation-workflow.md)

## Add a New Command

Create a class in `src/commands` that implements the `Command` interface, then register it in `src/index.ts`.
