# auth-service

Authentication service for the Research Diploma project.

## Overview

This service handles user authentication and authorization, including registration, login, session management, and token handling.

## Tech Stack

- **Runtime:** Node.js 20+
- **Framework:** Express.js
- **Language:** TypeScript
- **Database:** (see `.env.example` for connection details)

## Getting Started

### Prerequisites

- Node.js 20+
- pnpm

### Installation

```bash
pnpm install
```

### Environment Setup

Copy the example env file and fill in the required values:

```bash
cp .env.example .env
```

### Running Locally

```bash
pnpm dev
```

## API Documentation

Swagger UI is available at `/api-docs` when the server is running.

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening issues or pull requests. It covers the full claim/disclaim + PR linking flow used in this project.

## License

[Apache License 2.0](LICENSE)
