# Air-Gapped-AI-code-Verifer-
Air-Gapped AI Code Verifier is a full-stack MERN app for scanning codebases and verifying fixes entirely offline — no code or data leaves the network. Built for regulated environments where cloud AI review isn't an option. A simulated AST→GNN→SAE→Z3 pipeline finds issues and re-verifies fixes before acceptance.
# Air-Gapped AI Code Verifier v1.2

Full-stack application for offline AI-powered code verification.

## What's New in v1.2

### Security
- JWT authentication (login / register)
- Protected API routes
- Helmet security headers
- Rate limiting
- Restricted CORS
- Sanitized error responses
- `.env.example` for environment configuration
- Reduced JSON body limit

### Correctness
- Findings sorted by severity (critical, high, medium, low, info)
- Server-side pagination and search
- Database indexes on key fields
- Cascading deletes when a project is removed
- Database timestamps
- Consistent settings updates

### Repair Loop Improvements
- Multiple candidate fix generation
- Verification of each candidate
- Limited re-verification attempts
- Attempt counter on findings

### User Experience
- Login and logout
- Authentication-aware API client
- Clear error messages on findings

## Quick Start

### 1. Server

```bash
cd server
cp .env.example .env
npm install
npm run seed
npm run dev
```

### 2. Client

Open a new terminal:

```bash
cd client
npm install
npm start
```

Open the local URL displayed in your terminal.

## Technology Stack

- MongoDB
- Express.js
- React
- Node.js
- JavaScript
- CSS
- JWT authentication

## Air-Gapped Design

- No external telemetry
- Local database
- Offline operation after setup
- Local processing
- Browser-based PDF export

## Known Limitations

- Analysis pipeline may be simulated
- Real AI model integration may be incomplete
- Project import may support metadata only
- Automated tests may be incomplete
- Docker Compose may not be configured

## API

| Method | Path | Description |
|---|---|---|
| POST | `/api/auth/login` | Login |
| POST | `/api/auth/register` | Register |
| GET | `/api/auth/me` | Current user |
| GET | `/api/health` | Health check |
| GET | `/api/findings` | Search and paginate findings |
| POST | `/api/findings/:id/candidates` | Generate candidate fixes |
| POST | `/api/findings/:id/candidates/:idx/verify` | Verify a candidate |

## Version

1.2.0

## Author

Afiya Ali
