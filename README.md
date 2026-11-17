# DorsenAgentic AI — Cloudflare Pages starter

This is a deployment-ready **static foundation** for DorsenAgentic AI. It is a responsive Next.js 15 + React 19 + TypeScript site configured with `output: 'export'` for Cloudflare Pages static hosting.

## Important scope

This release is a visual product foundation only. The AI agent cards are concepts, not connected agents. There is no authentication, database, model API, persistent chat, app builder execution, payment, referral, or external-action automation yet. Do not enter secrets or sensitive information into this preview.

## Deploy using GitHub + Cloudflare Pages

1. Create a GitHub account and sign in.
2. Create a new repository named `dorsenagentic-ai`. Keep it private if preferred.
3. Upload the contents of this folder to the repository root (not the ZIP file itself).
4. In Cloudflare Dashboard, open **Workers & Pages → Create application → Pages → Connect to Git**.
5. Authorize GitHub and select `dorsenagentic-ai`.
6. Set build configuration:
   - Framework preset: **Next.js (Static HTML Export)** if shown; otherwise **None**
   - Build command: `npm run build`
   - Build output directory: `out`
   - Root directory: `/`
7. Save and deploy. Cloudflare will assign a `*.pages.dev` URL. In Pages project settings, check whether `dorsenagentic.pages.dev` is available; project names must be unique.

## Local development

Requires Node.js 20.9 or newer.

```bash
npm install
npm run dev
```

Open http://localhost:3000.

To verify the production static export:

```bash
npm run build
```

The exported website is written to `out/`.

## Future Supabase setup

`.env.example` lists placeholder public environment variables for a future client integration. No Supabase code is connected in this starter. Never put a Supabase service-role key or other private secret in a `NEXT_PUBLIC_` variable. Add authentication/database only in a later implementation and apply proper access policies.

## Cloudflare Pages limitations

This static export cannot run Next.js server components that require a server, API routes, server actions, or server-side rendering. Add those later through a compatible Cloudflare Workers/OpenNext architecture or a separate backend.
