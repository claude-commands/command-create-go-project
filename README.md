# command-create-go-project

Create a new Go web project with Echo, Templ, HTMX, Tailwind CSS, and sqlc.

## Installation

```bash
git clone git@github.com:corylanou/command-create-go-project.git ~/projects/command-create-go-project
ln -s ~/projects/command-create-go-project/create-go-project.md ~/.claude/commands/create-go-project.md
```

## Usage

```text
/create-go-project <project-name>
```

**Example:**

```text
/create-go-project my-app
```

## What It Does

1. Asks your database preference (PostgreSQL, SQLite, MySQL)
2. Asks about optional services (Clerk auth, Brevo email, Stripe payments)
3. Asks if you want an admin dashboard with dark/light mode
4. Asks your deployment platform (Vercel, Railway, Fly.io, self-hosted)
5. Creates a complete project structure with all files
6. Initializes git repository
7. Provides next steps to start developing

## Technology Stack

| Component | Technology |
|-----------|------------|
| Web Framework | Echo v4 |
| Templating | Templ |
| CSS | Tailwind CSS v4 |
| Interactivity | HTMX |
| Database | sqlc + goose |
| Hot Reload | Air |
| Logging | slog + tint |

## Project Structure Created

```text
project-name/
├── cmd/server/           # Entry point
├── internal/             # Go packages
│   ├── config/           # Environment config
│   ├── database/         # DB connection + sqlc
│   ├── handler/          # HTTP handlers
│   └── middleware/       # Echo middleware
├── templates/            # Templ templates
│   ├── layouts/          # Base layouts
│   ├── pages/            # Page templates
│   └── components/       # Reusable components
├── static/               # CSS, JS, images
├── migrations/           # goose migrations
├── sqlc/                 # SQL queries
├── .air.toml             # Hot reload config
├── .envrc.example        # Environment template
├── Makefile              # Build commands
└── go.mod                # Go module
```

## Database Options

- **PostgreSQL**: Uses `pgx/v5` driver, full feature support
- **SQLite**: Uses `modernc.org/sqlite` (CGO-free, pure Go)
- **MySQL**: Uses `go-sql-driver/mysql`

## Requirements

- Go 1.25+
- Node.js (for Tailwind CSS)
- direnv (recommended for environment management)

## Updates

```bash
cd ~/projects/command-create-go-project && git pull
```
