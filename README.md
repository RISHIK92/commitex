# AI-Powered Git Commit Message Generator

This repository provides a Git hook that uses an AI model (such as Ollama or Hugging Face) to automatically generate Conventional Commits-style commit messages based on your staged changes.

## Features

- Analyzes your staged git diff and generates a commit message using an AI model.
- Follows the [Conventional Commits](https://www.conventionalcommits.org/) specification.
- Opens the generated message in your editor for review and editing before finalizing the commit.

## Setup Instructions

1. **Clone or copy the `prepare-commit-msg` script to your project root.**

2. **Create a `.githooks` directory in your home folder:**

   ```sh
   mkdir -p ~/.githooks
   ```

3. **Move or copy the hook script into `.githooks`:**

   ```sh
   cp prepare-commit-msg ~/.githooks/
   # or
   mv prepare-commit-msg ~/.githooks/
   ```

4. **Make the script executable:**

   ```sh
   chmod +x ~/.githooks/prepare-commit-msg
   ```

5. **Configure Git to use your custom hooks directory:**

   ```sh
   git config --global core.hooksPath ~/.githooks
   ```

6. **Edit the script to set your AI model and API URL:**
   - Open `~/.githooks/prepare-commit-msg` in your editor.
   - Replace `MODEL_NAME_HERE` and `API_URL_HERE` with your model and endpoint.

## Usage

1. **Stage your changes:**

   ```sh
   git add .
   ```

2. **Commit:**
   ```sh
   git commit
   ```

   - The hook will:
     - Send the staged diff to your AI model.
     - Generate a Conventional Commit message.
     - Open your editor (e.g., Vim) to review and edit the message before finalizing the commit.

## Requirements

- Ensure your AI model server is running and accessible at the API URL you configured.
- The script requires `jq` and `curl` to be installed.

## Notes

- You can further customize the script for your workflow or model.
- For more information on Conventional Commits, visit [conventionalcommits.org](https://www.conventionalcommits.org/).
