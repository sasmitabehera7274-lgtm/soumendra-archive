SOUMENDRA ARCHIVE 2.0 — DEPLOYMENT NOTES

1) Open index.html and replace YOUR_SUPABASE_URL and YOUR_SUPABASE_ANON_KEY with the Supabase project URL and anon/public key.
   Find them in Supabase Dashboard -> Project Settings -> API (or API Keys). The anon/public key is intended for client use; never use or publish the service_role/secret key.
2) Save index.html.
3) Upload index.html to a GitHub repository named soumendra-archive (root of repo).
4) Import that repository into Vercel and deploy as a static site.
5) After Vercel gives the URL, Supabase -> Authentication -> URL Configuration:
   - Site URL: your deployed Vercel URL
   - Redirect URLs: add the same deployed URL
   Save changes.

IMPORTANT:
- Supabase RLS and Storage policies must be enabled. The SQL setup previously run in the project is expected to be in place.
- Supabase Storage bucket archive-files should remain PRIVATE.
- Do not publish the service_role key or database password.
- If email confirmation is enabled, confirm the sign-up email before sign-in.
- This prototype currently stores one user's files under their own user UUID path. Keep the policies in place.
