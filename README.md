# Anthropic Claude Data Import Plugin

A community plugin for importing your conversation history and data from Anthropic Claude.

## Supported Data Types

This plugin imports the following data from Anthropic Claude exports:

- **Conversations** - Your chat history with Claude, including message counts
- **Memories** - Claude's learned context about you (if enabled)
- **Projects** - Your Claude projects and associated documents

## Installation

### From Git

```bash
# Install via MeDB
medb plugins:install github:medb-community/anthropic-import
```

### From Local Directory

```bash
# For development/testing
medb plugins:install-local ./path/to/anthropic-import
```

## How to Export Your Data

1. Go to [claude.ai](https://claude.ai) and sign in
2. Click your profile icon in the bottom-left corner
3. Select **Settings** from the menu
4. Navigate to the **Account** section
5. Click **Request Data Export** or **Download Your Data**
6. Confirm your request via email if required
7. Wait for the export (typically 24-48 hours)
8. Download the ZIP file when ready

## Data Format

Anthropic exports data as a ZIP file containing:

```
data-YYYY-MM-DD-HH-MM-SS-batch-XXXX/
  conversations.json    # Your chat history
  memories.json         # Claude's learned context
  projects.json         # Your projects and documents
  users.json            # Account information
```

## Event Types Generated

| Source File | Event Type | Description |
|-------------|------------|-------------|
| conversations.json | `chat` | One event per conversation |
| memories.json | `ai_memory` | Memory snapshot of Claude's context |
| projects.json | `project` | One event per project |

## Privacy Notes

- This plugin only processes data locally on your machine
- No data is sent to external servers
- Your exported data remains under your control

## License

MIT
