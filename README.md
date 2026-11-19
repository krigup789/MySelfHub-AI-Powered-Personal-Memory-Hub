# SelfHub – AI-Powered Personal Memory Hub

**A personal AI memory management system built using the Model Context Protocol (MCP), Node.js, TypeScript, and MongoDB.**

SelfHub allows AI assistants to store, retrieve, search, and organize personal information across different conversations.

## Overview

SelfHub is an MCP server that acts as a persistent personal memory hub. It helps AI assistants remember useful information such as:

- Personal preferences
- Project details
- Learning notes
- Tasks and reminders
- Code snippets
- Important information

Memories can be accessed through MCP-compatible clients such as Claude Desktop, Claude Code, and VS Code with GitHub Copilot.

## Key Features

- **Memory Management:** Store, retrieve, search, list, and delete memories.
- **Context Management:** Organize memories into separate contexts.
- **Text Search:** Search stored memories using MongoDB text indexing.
- **Memory Categorization:** Organize information using categories and tags.
- **Analytics:** View memory statistics and usage insights.
- **Persistent Storage:** Store data in MongoDB.
- **MCP Integration:** Connect with compatible AI assistants.
- **Docker Support:** Run the application using Docker Compose.

## Technology Stack

| Technology | Purpose |
|---|---|
| Node.js | Runtime environment |
| TypeScript | Application development |
| Model Context Protocol (MCP) | AI assistant integration |
| MongoDB | Database |
| Mongoose | MongoDB object modeling |
| pnpm | Package management |
| Docker | Containerization |
| Node.js Test Runner | Automated testing |

## Architecture

The application follows a layered architecture:

1. **MCP Server:** Handles MCP requests and tool execution.
2. **Services Layer:** Contains memory and context business logic.
3. **Storage Layer:** Manages persistent MongoDB operations.
4. **Models:** Defines application data structures.

AI clients communicate with the server using JSON-RPC over standard input/output (stdio).

## Available MCP Tools

SelfHub provides nine tools in three categories.

### 1. Memory Management

- `store_memory` – Store a new memory.
- `retrieve_memory` – Retrieve a memory using its ID.
- `list_memories` – List memories with optional filters.
- `search_memories` – Search memories using text queries.
- `delete_memory` – Delete a memory.

### 2. Context Management

- `create_context` – Create a context for organizing memories.
- `activate_context` – Activate a context and load its memories.
- `list_contexts` – List available contexts.

### 3. Analytics

- `get_stats` – View memory statistics, categories, types, and tags.

## Project Structure

```text
SelfHub/
├── src/
│   ├── index.ts
│   ├── seed.ts
│   ├── db/
│   ├── models/
│   ├── services/
│   └── storage/
├── test/
├── scripts/
├── Dockerfile
├── docker-compose.yml
├── package.json
├── tsconfig.json
├── .env.example
└── README.md
```

## Installation and Setup

### Prerequisites

- Node.js 24+
- pnpm
- MongoDB

### 1. Clone the repository

```bash
git clone https://github.com/krigup789/MySelfHub-AI-Powered-Personal-Memory-Hub.git
cd MySelfHub-AI-Powered-Personal-Memory-Hub
```

### 2. Install dependencies

```bash
pnpm install
```

### 3. Configure environment variables

Create a `.env` file using the example:

```bash
cp .env.example .env
```

Configure your MongoDB connection string:

```env
MONGODB_URI=mongodb://localhost:27017/selfhub
```

### 4. Build the project

```bash
pnpm build
```

### 5. Run the project

```bash
pnpm dev
```

## Available Commands

| Command | Description |
|---|---|
| `pnpm dev` | Start development mode |
| `pnpm build` | Build the project |
| `pnpm typecheck` | Run TypeScript checks |
| `pnpm test` | Run automated tests |
| `pnpm seed` | Load sample data |
| `pnpm demo` | Run the cross-client demonstration |
| `pnpm clean` | Clean the build directory |

## Testing

Run the automated test suite:

```bash
pnpm test
```

The project includes end-to-end tests for MCP tools, memory operations, context management, database interactions, and server lifecycle behavior.

## Docker Setup

Build the Docker image:

```bash
docker compose build
```

Start MongoDB:

```bash
docker compose up -d mongo
```

Refer to the Docker Compose configuration for the server startup process.

## Future Enhancements

- Semantic search using vector embeddings
- File import and export
- Data encryption
- Web-based management dashboard
- Multi-user support
- Cloud synchronization

## License and Attribution

This project is distributed under the MIT License. Refer to the included `LICENSE` file for the complete license terms.

**Attribution:** This project is based on the original SelfHub project. Original authorship and copyright notices are retained. Additional modifications and contributions should be credited separately.

---

**Maintained by:** [Krish Gupta](https://github.com/krigup789)

**Repository:** [MySelfHub-AI-Powered-Personal-Memory-Hub](https://github.com/krigup789/MySelfHub-AI-Powered-Personal-Memory-Hub)
