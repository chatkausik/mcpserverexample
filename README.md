# MCP Server Installation Guide

This repository contains multiple MCP (Model Context Protocol) server implementations and clients. Follow the instructions below to install and configure the MCP server.

## Prerequisites

- Python 3.8 or higher
- `uv` package manager
- Git

## Installation

### Step 1: Install uv (if not already installed)

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### Step 2: Install the MCP Server

You can install the MCP server directly from the GitHub repository using uvx:

```bash
uvx --from git+https://github.com/chatkausik/mcpserverexample.git mcp-server
```

### Step 3: Configuration

Add the following configuration to your MCP client configuration file (usually `claude_desktop_config.json` or similar):

```json
{
  "mcpServers": {
    "add_tool": {
      "command": "/Users/kausik/.langflow/uv/uvx",
      "args": [
        "--from",
        "git+https://github.com/chatkausik/mcpserverexample.git",
        "mcp-server"
      ]
    }
  }
}
```

**Note:** Replace `uvx` with your actual path to the uvx executable. You can find it by running:

```bash
which uvx
```

### Step 4: Verify Installation

Test your MCP server configuration by starting your MCP client. The server should be automatically loaded and available for use.

## Local Development

If you want to run the server locally for development:

1. Clone this repository:

```bash
git clone https://github.com/chatkausik/mcpserverexample.git
cd mcpserverexample
```

2. Sync dependencies:

```bash
uv sync
```

3. Run the server:

```bash
uv run mcp-server
```

## Available Projects

This workspace contains several MCP-related projects:

- **CLIENT** - MCP client implementations
- **mcp-server-deepdive-deployment** - Server deployment examples
- **mcp-server-deepdive-functionality** - Core server functionality
- **mcp-build-*** - Various MCP build configurations
- **quickstart** - Quick start examples

## Troubleshooting

### Common Issues

- **Command not found**: Ensure `uvx` is in your PATH
- **Permission errors**: Make sure you have write permissions to the installation directory
- **Network issues**: Verify you have internet access to download from GitHub

### Getting Help

If you encounter issues:

1. Check the server logs for error messages
2. Verify your configuration matches the example above
3. Ensure all prerequisites are installed correctly

## Contributing

Please refer to the individual project directories for specific contribution guidelines.