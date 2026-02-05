# Toolkit Build Walkthrough

This walkthrough mirrors the steps used to create the CLI AI Toolkit.

## Step 1: Define the architecture

- Choose a command registry pattern.
- Separate commands, services, and core utilities.
- Decide on output conventions (`references/`, `images/`).

## Step 2: Scaffold the project

- Initialize Node.js + TypeScript.
- Add linting and formatting.
- Create entrypoint and registry.

## Step 3: Add web search

- Create a `web-search` command.
- Use OpenAI web search tools.
- Persist outputs to `references/` with timestamped names.

## Step 4: Add Gemini integration

- Add a Gemini service with API key support.
- Implement `gemini` command for prompt + media.
- Store responses in `references/aI_feedback/`.

## Step 5: Add image generation

- Add `image-generate` command.
- Save images to `images/` with prompt-based filenames.

## Step 6: Document the system

- Update README with orchestration guidance.
- Create docs that teach the workflow.

## Step 7: Iterate with feedback

- Review outputs, adjust styles, and refine commands.
