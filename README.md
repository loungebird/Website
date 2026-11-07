![Site](.readme/site.png)

# Loungebird Website

Landing page for Loungebird - real-time lounge occupancy insights for London Heathrow Terminal 5.

## Tech Stack

- React 19 + TypeScript
- Vite
- Framer Motion (animations)
- React Router (SPA routing)
- CSS Modules

## Development

### Prerequisites

- Node.js 26 and npm, for bootstrapping pnpm
- pnpm 12 (the project provisions the version pinned in `package.json`)

Install the pinned pnpm version using npm:

```bash
npm install -g "pnpm@$(node -p 'require("./package.json").devEngines.packageManager.version')"
```

pnpm downloads the Node.js runtime declared in `package.json` during installation and uses it for project scripts. Verify the selected versions with `pnpm --version` and `pnpm exec node --version`.

### Install dependencies

```bash
pnpm install --frozen-lockfile
```

### Start development server

```bash
pnpm dev
```

### Build for production

```bash
pnpm build
```

### Preview production build

```bash
pnpm preview
```

## Deployment

### Vercel

The site automatically deploys to Vercel on pushes. Pushes to `main` will deploy to production. Vercel selects the Node.js major version from `engines.node` and the pnpm version from `devEngines.packageManager` in `package.json`.

### Docker

The Docker builder bootstraps the pnpm version from `package.json` and installs the project-managed Node runtime. CI uses the same manifest declarations. Build and run with Docker:

```bash
# Build the image
docker build -t loungebird-website .

# Run the container
docker run -p 8080:80 loungebird-website
```

Or use Docker Compose:

```bash
docker compose up
```
