# A.S.S. Lover — Frontend

> React + TypeScript frontend for the A.S.S. Lover system.

## Overview

The frontend provides the user interface for interacting with the A.S.S. Lover system — an intelligent platform for web content ingestion and RAG-powered search.

## Features

### RAG Search (`/search`)
- Natural language querying
- Toggle between RAG and no-RAG modes
- Citation display for source documents
- Extracted file previews
- Results export

### Ingestion Management (`/ingestion`)
- Add and configure web sources
- Deep crawl configuration (depth, strategy)
- Legal basis selection (public, consent, contract)
- Auto-scheduling
- Job monitoring and incident resolution (CAPTCHA detection)

### Analytics (`/analytics`)
- System statistics overview
- Job status breakdown
- Ingestion strategy metrics
- Evidence artifact browsing (screenshots, markdown files)

## Tech Stack

| Component | Technology |
|---|---|
| Framework | React 18 + TypeScript |
| Build Tool | Vite |
| Styling | Tailwind CSS |
| Animations | Framer Motion |
| Auth | Keycloak JS (`keycloak-js`) |
| Icons | Lucide React |

## Authentication

The frontend implements the Keycloak OIDC flow:
1. User login triggers a redirect to Keycloak.
2. Upon successful login, Keycloak returns a JWT access token.
3. The token is stored in memory and sent with every API request.
4. An Axios interceptor automatically refreshes the token before it expires.

## Configuration

### Environment Variables
Vite uses variables prefixed with `VITE_`.
```bash
VITE_KEYCLOAK_URL=https://your-server-ip/auth
```

## Local Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Run development server:
   ```bash
   npm run dev
   ```
   The server will run on `http://localhost:5173`.

## Build and Deployment

```bash
npm run build
```
The output will be generated in the `dist/` directory. For production deployment via Docker, see [ass-lover-infra](https://github.com/Deatrix09/ass-lover-infra).

## License

MIT
