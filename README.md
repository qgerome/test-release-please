# Full Stack Application

This project consists of:
- Django backend (in `/backend`)
- Next.js frontend (in `/frontend`)

## Development

### Backend

```bash
cd backend
python -m pip install -e ".[dev]"
python manage.py runserver
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

## Release Process

This project uses [release-please](https://github.com/googleapis/release-please) to manage releases and versioning. The release process is automated:

1. Make changes and follow [Conventional Commits](https://www.conventionalcommits.org/) format for commit messages:
   - `feat: add new feature` (bumps minor version)
   - `fix: resolve issue` (bumps patch version)
   - `feat!: breaking change` or `chore!: drop support for Node 14` (bumps major version)

2. When your PR is merged to main, release-please will:
   - Create or update a release PR
   - Track changes across the monorepo
   - Maintain a single version number for all components

3. When the release PR is merged:
   - A new GitHub release will be created
   - Version numbers are updated automatically in:
     - `frontend/package.json`
     - `backend/pyproject.toml` 