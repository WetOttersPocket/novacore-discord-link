# NovaCore Discord link page (GitHub Pages)

Static page used by the QR in Nova (Quick menu > Friends > Link Discord). No secrets.

1. On GitHub create a **public** repo named `novacore-discord-link` (any name works, but the URL changes).
2. Upload `index.html` (and this README) to the repo root, branch `main`.
3. Repo **Settings > Pages**: Source = *Deploy from a branch*, Branch = `main` / `(root)`, Save. Wait ~1 min.
4. The page is now at `https://<your-github-username>.github.io/novacore-discord-link/`.
5. Discord developer portal > app **1558983913588662342** > **OAuth2**:
   - Redirects > Add: `https://<your-github-username>.github.io/novacore-discord-link/` (exact, with the trailing slash). Save.
   - Turn **Public Client** ON (PKCE without a secret). If you leave it off, set `DISCORD_CLIENT_SECRET` as an environment variable for the presence service instead; never commit it.
6. On the PC copy `companion\nova-presence-service\link-config.example.json` to `link-config.json` and replace `<your-github-username>` in both lines. Restart the presence service.
