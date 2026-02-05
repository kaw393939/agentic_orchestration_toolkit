# CLI AI Toolkit

A SOLID-friendly Node.js CLI for AI utilities.

This repo is also a teaching lab for AI orchestration: breaking work into clear goals, giving the agent tools and constraints, and iterating with feedback.

## Setup

1. Install dependencies:

   npm install

2. Ensure your `.env` file includes:

   OPENAI_API_KEY=your_key_here
   GEMINI_API_KEY=your_key_here

## Usage

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

## Student Walkthroughs

- [AI orchestration playbook](docs/orchestration-playbook.md)
- [Toolkit build walkthrough](docs/toolkit-build-walkthrough.md)
- [Image generation workflow](docs/image-generation-workflow.md)

## Add a New Command

Create a class in `src/commands` that implements the `Command` interface, then register it in `src/index.ts`.
