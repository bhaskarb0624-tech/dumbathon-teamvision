# DUMBATHON - TEAM VISION

A TypeScript monorepo workspace featuring multiple web applications and shared libraries, built with modern tooling and best practices.

## 🚀 Projects

### MADLOG - Horror Journal App
A psychological horror journaling experience where a paranoid AI progressively sabotages the user through 4 stages of madness.

**Features:**
- 4-stage madness progression (Normal → Paranoid → Sarcastic → Insanity)
- Chaos popup engine with exponential virus behavior
- Keyword detection triggering contextual horror responses
- Silent entry corruption and data manipulation
- Hacker breach sequence with full-screen takeover
- Secret ending at 5 minutes (corrupts all journal data)
- Cursor madness effects and visual glitches
- Web Audio API for atmospheric horror sounds
- CSS glitch effects, screen flicker, and CRT scanlines

### Mockup Sandbox
An interactive mockup preview and testing environment for rapid prototyping.

### API Server
Express 5 REST API server with PostgreSQL database integration.

## 🛠️ Tech Stack

- **Monorepo**: pnpm workspaces
- **Runtime**: Node.js 24
- **Language**: TypeScript 5.9
- **Frontend**: React 19, Vite, TailwindCSS 4
- **Backend**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod v4
- **API Codegen**: Orval (OpenAPI)
- **Build**: esbuild

## 📁 Project Structure

```
Asset-Manager/
├── artifacts/              # Deployable applications
│   ├── madlog/            # Horror journal app
│   ├── mockup-sandbox/    # Mockup preview tool
│   └── api-server/        # Express API server
├── lib/                   # Shared libraries
│   ├── api-spec/          # OpenAPI spec + Orval config
│   ├── api-client-react/  # Generated React Query hooks
│   ├── api-zod/           # Generated Zod schemas
│   └── db/                # Drizzle ORM schema + DB connection
├── scripts/               # Utility scripts
├── attached_assets/       # Shared assets
├── pnpm-workspace.yaml    # Workspace configuration
├── tsconfig.base.json     # Shared TypeScript config
└── package.json           # Root package
```

## 🚦 Getting Started

### Prerequisites

- Node.js 24+
- pnpm 9+
- PostgreSQL (for API server)

### Installation

```bash
# Install dependencies
pnpm install

# Build all packages
pnpm run build

# Type check all packages
pnpm run typecheck
```

### Development

#### MADLOG Horror Journal
```bash
# Set required environment variables
export PORT=3000
export BASE_PATH=/

# Start development server
pnpm --filter @workspace/madlog run dev
```

#### Mockup Sandbox
```bash
# Set required environment variables
export PORT=3001
export BASE_PATH=/

# Start development server
pnpm --filter @workspace/mockup-sandbox run dev
```

#### API Server
```bash
# Set database URL
export DATABASE_URL=postgresql://user:password@localhost:5432/dbname

# Start development server
pnpm --filter @workspace/api-server run dev

# Push database schema
pnpm --filter @workspace/db run push
```

## 📦 Workspace Packages

### Applications (`artifacts/`)

- **@workspace/madlog** - Horror journal React app
- **@workspace/mockup-sandbox** - Mockup preview tool
- **@workspace/api-server** - Express REST API

### Libraries (`lib/`)

- **@workspace/api-spec** - OpenAPI specification and codegen
- **@workspace/api-client-react** - Generated React Query hooks
- **@workspace/api-zod** - Generated Zod validation schemas
- **@workspace/db** - Database layer with Drizzle ORM

### Utilities

- **@workspace/scripts** - Utility scripts for development

## 🔧 TypeScript Configuration

This workspace uses TypeScript composite projects with project references:

- Always typecheck from the root: `pnpm run typecheck`
- Uses `emitDeclarationOnly` - actual bundling handled by esbuild/vite
- Cross-package imports resolve through project references

## 📝 Scripts

```bash
# Build all packages
pnpm run build

# Type check all packages
pnpm run typecheck

# Type check libraries only
pnpm run typecheck:libs

# Generate API client from OpenAPI spec
pnpm --filter @workspace/api-spec run codegen

# Database migrations
pnpm --filter @workspace/db run push
pnpm --filter @workspace/db run push-force
```

## 🎨 UI Components

Both frontend applications use:
- Radix UI primitives
- TailwindCSS 4 with custom design tokens
- shadcn/ui component patterns
- Framer Motion for animations
- React Hook Form + Zod validation

## 🗄️ Database

The database layer uses:
- Drizzle ORM for type-safe queries
- PostgreSQL as the database
- Zod schemas generated from Drizzle tables
- Connection pooling with `pg`

## 🌐 Deployment

### Quick Deploy (No GitHub Required)

The app is pre-built and ready to deploy. Build files are in `artifacts/madlog/dist/public`.

#### Option 1: Netlify Drop (Easiest - 2 Minutes)
1. Go to https://app.netlify.com/drop
2. Drag the `artifacts/madlog/dist/public` folder
3. Done! Get instant live URL

#### Option 2: Surge CLI (Fastest)
```bash
npm install -g surge
cd artifacts/madlog/dist/public
surge
```

#### Option 3: Vercel, Render, Cloudflare Pages
See [DEPLOYMENT.md](DEPLOYMENT.md) for detailed instructions.

### Rebuild for Updates
```bash
cd Asset-Manager
pnpm --filter @workspace/madlog run build
```

📖 **Full deployment guide**: [DEPLOYMENT.md](DEPLOYMENT.md)  
📖 **Manual deployment guide**: [MANUAL_DEPLOY.md](MANUAL_DEPLOY.md)

## 🔐 Environment Variables

### MADLOG & Mockup Sandbox
- `PORT` - Server port (required)
- `BASE_PATH` - Base URL path (required)

### API Server
- `DATABASE_URL` - PostgreSQL connection string (required)
- `PORT` - Server port (default: 3000)
- `NODE_ENV` - Environment (development/production)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run `pnpm run typecheck` to ensure no errors
5. Submit a pull request

## 📄 License

MIT

## 👥 Team

DUMBATHON - TEAM VISION

## 🔗 Repository

https://github.com/Bhaskar0624/DUMBATHON-TEAM-VISION
