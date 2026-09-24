# Chris AI

Chris AI is a modern AI-powered assistant designed for chat, business automation, content generation, and productivity.

## Features

- AI chat assistant
- Voice input and output
- Secure authentication
- Business dashboard
- Payment integration hooks
- Multi-device support
- Cloud synchronization
- Analytics and reporting

## Installation

```bash
git clone https://github.com/akibuchristian842-crypto/chris-ai.git
cd chris-ai
npm install
```

Copy the environment template and configure your local services:

```bash
cp .env.example .env
```

## Start the application

The project uses an npm workspace monorepo. Start the frontend and backend together with:

```bash
npm run dev
```

Or start each workspace independently:

```bash
npm run dev --workspace @chris-ai/web
npm run dev --workspace @chris-ai/api
```

The frontend runs at `http://localhost:3000` and the API runs at `http://localhost:4000`.

## Database

Start PostgreSQL with Docker, then generate the Prisma client and apply the schema:

```bash
docker compose up -d postgres
npm run db:generate
npm run db:push
```

## Production build

```bash
npm run lint
npm test
npm run build
```

## Backend API

The API supports authentication, conversations, AI messaging, file-analysis hooks, usage tracking, and health checks. Configure `OPENAI_API_KEY`, `DATABASE_URL`, and secure JWT values in `.env` before enabling production services.

## Deployment

- Deploy the Next.js frontend to Vercel or another Node-compatible platform.
- Deploy the Express API to a container platform such as Railway, Render, or Fly.io.
- Use a managed PostgreSQL provider and configure production secrets through the platform secret manager.
- Run CI checks from `.github/workflows/ci.yml` on every pull request and push.

## Security

Never commit `.env` files or production credentials. Use strong, unique secrets, enforce HTTPS in production, validate request payloads, and configure rate limits appropriate to your deployment.

## License

MIT License
