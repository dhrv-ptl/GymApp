# IronTrack

A personal gym tracking web app built with React, Vite, and Supabase. Log workouts, manage training programs, and monitor your progress over time.

## Features

- **Authentication** – Sign up and sign in with Supabase Auth.
- **Training Programs** – Create and organize multi-day workout programs.
- **Workout Logging** – Record sets, reps, and weights for each exercise.
- **Dashboard** – View recent activity and progress at a glance.
## Tech Stack

| Layer | Library / Service |
|---|---|
| UI | React 19, Tailwind CSS v4, Radix UI |
| Routing | React Router v7 |
| Backend / DB | Supabase (Postgres + Auth) |
| Build | Vite 6 |
| Server | Express (dev & production SSR shell) |

## Getting Started

### Prerequisites

- Node.js 18+
- A [Supabase](https://supabase.com) project

### Installation

```bash
# Install dependencies
npm install

# Copy the example env file and fill in your values
cp .env.example .env
```

Edit `.env` and set at minimum:

```
VITE_SUPABASE_URL=https://<your-project-id>.supabase.co
VITE_SUPABASE_ANON_KEY=<your-anon-key>
```

### Database

Apply the schema to your Supabase project:

```bash
# From the Supabase dashboard SQL editor, or via the CLI:
supabase db push  # if using Supabase CLI
# — OR —
# Paste the contents of supabase_migration.sql into the SQL editor and run it.
```

### Development

```bash
npm run dev
# App is available at http://localhost:3000
```

### Production Build

```bash
npm run build   # Outputs to dist/
npm start       # Serves the built app via Express
```

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `VITE_SUPABASE_URL` | ✅ | Your Supabase project URL |
| `VITE_SUPABASE_ANON_KEY` | ✅ | Your Supabase anonymous (public) key |
| `APP_URL` | Optional | Base URL of the app (used for OAuth callbacks) |

## Project Structure

```
├── src/
│   ├── features/        # Feature modules (auth, dashboard, programs, workout-log, …)
│   ├── components/      # Shared UI components
│   ├── lib/             # Supabase client, utilities
│   └── main.tsx         # Application entry point
├── server.ts            # Express server (dev + prod)
├── vite.config.ts       # Vite configuration
├── supabase_migration.sql  # Database schema
└── .env.example         # Environment variable template
```

## License

MIT
