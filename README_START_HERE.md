# The Keiber Cortex — Deployment starter

This package includes the existing single-file website, renamed `index.html` for static hosting. All artwork that was embedded in the previous offline version remains embedded.

## Important security note
This is a **public design prototype**, NOT a secure editing system. Its editor uses browser localStorage. It has no owner authentication or shared database. Do not enter private journal content or assume the Publish toggle makes content available to visitors. Do not share a browser/device containing your drafts.

## Publish for free using GitHub + Vercel
1. Create a GitHub account at https://github.com/signup (if needed).
2. Create a new **private** repository named `the-keiber-cortex`.
3. Upload `index.html` from this folder to the repository (Add file → Upload files → Commit changes). Do not upload secrets, journal backups, API keys, or private drafts.
4. Sign up at https://vercel.com/signup and choose the Hobby plan if eligible.
5. In Vercel, choose Add New → Project, import your private GitHub repository, keep the framework preset as Other, and deploy.
6. Vercel will give you a `.vercel.app` URL. Anyone with the URL can see the website, but GitHub repository editing stays restricted to your GitHub account.

## What this does NOT do yet
- The website's browser-only editing studio is **not access-controlled**. Visitors can open its controls, but their local edits do not update your deployed site.
- The AI companion is a rule-based demo, not a live AI model.
- There is no server-side content database, moderation, owner sign-in, or AI change approval system.

## Secure next phase (requires account setup)
1. Create a Supabase project and set up owner-only authentication and row-level security.
2. Migrate published articles into public-read / owner-write tables; keep drafts owner-only.
3. Move the editing dashboard behind authentication and remove all browser-only publishing claims.
4. Add an authenticated server endpoint for a supported AI provider with a free tier, rate limits, and approval-before-save. Never put an AI API key in client HTML.
5. Test as a logged-out visitor to confirm no unauthorized read/write access.

Free service tiers can change, pause, or impose quotas; live AI cannot be promised as unlimited and permanently free.
