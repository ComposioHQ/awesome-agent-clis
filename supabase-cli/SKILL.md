---
name: "Supabase CLI"
description: "Manage Postgres databases, auth, edge functions, storage, and local dev environments. Use when an agent needs to manage Supabase projects, run database migrations, deploy edge functions, or start a local Supabase stack."
---

# Supabase CLI

Manage Postgres databases, auth, edge functions, and storage.

- **Repo**: https://github.com/supabase/cli
- **Docs**: https://supabase.com/docs/guides/cli

## Installation

```bash
npx supabase --help
```

## Key Commands

```bash
npx supabase init
npx supabase start                    # local dev stack
npx supabase db push                  # apply migrations
npx supabase db diff --schema public  # generate migration
npx supabase functions deploy my-func
npx supabase gen types typescript --local
npx supabase migration new my_change
npx supabase db reset
npx supabase link --project-ref <ref>
npx supabase secrets set KEY=value
```

## Agent-Friendly Features

- Local development with `supabase start`
- Database diffing and migration generation
- TypeScript type generation from schema
- Edge function deployment
- Token auth via `SUPABASE_ACCESS_TOKEN`
