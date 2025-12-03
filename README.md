# Biome Custom Rules Sample App

This is a [Next.js](https://nextjs.org) project that demonstrates how to use [Biome](https://biomejs.dev/) with custom rules created using [Grit](https://grit.io/). The project showcases how to extend Biome's linting capabilities with custom rules and integrate them into a development workflow using Husky for pre-commit hooks.

## Features

- Next.js 14 with App Router
- Biome for code formatting and linting
- Custom Biome rules created with Grit
- Husky pre-commit hooks to enforce code quality
- Example custom rules:
  - `no-console`: Prevents console statements in production code
  - `reportassign`: Reports assignment expressions in specific contexts

## Getting Started

First, install dependencies:

```bash
npm install
# or
yarn install
# or
pnpm install
```

Then, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

## Biome Commands

### Linting and Formatting

```bash
# Check code for issues
npm run lint

# Fix auto-fixable issues
npm run lint:fix

# Format code
npm run format

# Check formatting without making changes
npm run format:check
```

### Custom Rules

The custom Biome rules are defined in the `grit-rules/` directory:

- `no-console.grit`: Prevents console statements in production code
- `reportassign.grit`: Reports assignment expressions in specific contexts

These rules are automatically loaded by Biome through the configuration in `biome.json`.

## Husky Pre-commit Hooks

This project uses Husky to run checks before each commit. The pre-commit hook is defined in `.husky/pre-commit` and performs the following checks:

1. Runs Biome linting to check for code issues
2. Runs Biome formatting check to ensure consistent code style
3. Prevents the commit if any issues are found

### Testing Pre-commit Hooks

To test how Husky checks pre-commit:

1. Make a change to any file in the project
2. Try to commit the change:
   ```bash
   git add .
   git commit -m "Test commit"
   ```
3. If there are any linting or formatting issues, the commit will be blocked and you'll see the errors
4. Fix the issues by running:
   ```bash
   npm run lint:fix
   npm run format
   ```
5. Try committing again

### Bypassing Pre-commit Hooks (Not Recommended)

If you need to bypass the pre-commit hooks (not recommended for normal development):

```bash
git commit --no-verify -m "Your commit message"
```

## Learn More

To learn more about the technologies used in this project:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API
- [Biome Documentation](https://biomejs.dev/) - learn about Biome's features and configuration
- [Grit Documentation](https://grit.io/docs) - learn about creating custom rules with Grit
- [Husky Documentation](https://typicode.github.io/husky/) - learn about Git hooks

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
