# MCP Bookmark Manager Example

This is a [Model Context Protocol (MCP)](https://modelcontextprotocol.io) server built with [Zuplo](https://zuplo.com) that demonstrates how to implement MCP tools and prompts using an OpenAPI-defined API.

## What This Example Includes

This project implements a **Bookmark Manager** with MCP integration that showcases:

### MCP Tools
- **`list-bookmarks`** - List saved bookmarks with optional tag filtering
- **`save-bookmark`** - Save a new bookmark with URL, title, and tags
- **`delete-bookmark`** - Delete a bookmark by ID

### MCP Prompts
- **`research-roundup`** - An AI prompt that analyzes recent bookmarks to identify research patterns, themes, and suggest next steps

### Key Components
- **OpenAPI-based Routes** (`config/routes.oas.json`) - API routes with MCP annotations
- **Bookmark Handlers** (`modules/bookmarks.ts`) - CRUD operations with cache-based storage
- **Research Prompt** (`modules/research-roundup-prompt.ts`) - Custom MCP prompt implementation
- **Built-in Documentation** (`docs/`) - Zudoku-powered API documentation

## Getting Started

### Prerequisites

- Node.js 18 or later
- npm, yarn, or pnpm

### Installation

```bash
npm install
```

### Running Locally

Start the development server:

```bash
npm run dev
```

The API will be available at [http://localhost:9000](http://localhost:9000).

You can access:
- **API Gateway** - `http://localhost:9000`
- **Local API Route Designer** - `http://localhost:9100`
- **MCP Endpoint** - `http://localhost:9000/mcp` (POST)

The dev server will automatically reload when you modify:
- Route definitions in `config/routes.oas.json`
- Handler modules in `modules/`

## Deploying with Zuplo CLI

### Install the Zuplo CLI

```bash
npm install -g zuplo
```

### Login to Zuplo

```bash
zuplo login
```

### Create a New Project

```bash
zuplo init
```

Follow the prompts to create a new project in your Zuplo account.

### Deploy to Zuplo

Deploy to a working copy environment:

```bash
zuplo deploy
```

Or deploy to production:

```bash
zuplo deploy --prod
```

## Using the MCP Server

Once deployed, you can connect to your MCP server using any MCP client (like Claude Desktop). Configure your MCP client to point to:

```
https://your-project.zuplo.app/mcp
```

The server will expose:
- 3 tools for managing bookmarks
- 1 prompt for analyzing your research patterns

## Learn More

- [Zuplo Documentation](https://zuplo.com/docs)
- [Model Context Protocol Docs](https://modelcontextprotocol.io)
- [Building MCP Servers with Zuplo](https://zuplo.com/blog/2024/12/16/building-mcp-servers-with-zuplo)
- [Join Zuplo Discord](https://discord.zuplo.com)
