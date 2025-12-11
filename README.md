# Dropbox Paper Export

Tool to export Dropbox Paper documents to Markdown files with embedded images downloaded locally.

## Features

- Exports all `.paper` documents from a Dropbox folder (including subfolders) to Markdown format
- Downloads and saves images locally, updating markdown links to reference local files
- Supports both personal and team Dropbox accounts
- Shows progress with a progress bar during export
- Preserves folder structure from Dropbox

## How It Works

1. Connects to Dropbox using the API
2. Recursively scans for `.paper` files in the specified directory
3. Exports each document to Markdown format using Dropbox's export API
4. Scans the exported markdown for image links
5. Downloads each image and saves it to a local `assets/` folder
6. Updates the markdown to reference the local image paths

## Requirements

- Python 3.12+
- Dropbox API access token with appropriate permissions

## Installation

```bash
# Install uv (if not already installed)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Install dependencies
uv sync
```

## Usage

1. Create a Dropbox App at https://www.dropbox.com/developers/apps
2. Generate an access token with the following permissions:
   - `account_info.read`
   - `files.metadata.read`
   - `files.content.read`
   - `sharing.read`
3. Run the exporter:

```bash
uv run main.py --access-token ACCESS_TOKEN
```
