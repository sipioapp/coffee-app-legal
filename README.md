# Sipio Legal Web (GitHub Pages)

Public legal pages for **Sipio: Coffee Journal & Brews**, hosted separately from the main app repository.

| Page | URL (after Pages is enabled) |
|------|------------------------------|
| Privacy Policy | https://sipioapp.github.io/coffee-app-legal/privacy_policy.html |
| Account Deletion | https://sipioapp.github.io/coffee-app-legal/delete_account.html |

## Files

- `privacy_policy.html` — Privacy Policy (Name, Email, Precise Location; no tracking/ads)
- `delete_account.html` — In-app automated account deletion instructions (Settings > Delete Account)

## One-time setup & push (sipioapp account)

Run these commands from this folder. Replace `YOUR_NEW_TOKEN` with a PAT from the **sipioapp** GitHub account.

```bash
cd ~/sipio-legal-web

# Local git identity for this repo only (does not change global Cursor login)
git config user.name "sipioapp"
git config user.email "YOUR_SIPIOAPP_EMAIL@example.com"

git init
git branch -M main
git add privacy_policy.html delete_account.html README.md
git commit -m "Add Sipio privacy policy and account deletion pages"

# Add remote (optional if you only push via URL below)
git remote add origin https://github.com/sipioapp/coffee-app-legal.git

# Push using HTTPS + PAT (bypasses your personal SSH key)
git push https://YOUR_NEW_TOKEN@github.com/sipioapp/coffee-app-legal.git main
```

### Generate PAT on sipioapp

1. Log in to GitHub as **sipioapp** (not your personal account).
2. **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**.
3. **Generate new token (classic)**.
4. Note: e.g. `sipio-legal-pages-push`.
5. Expiration: 7 or 30 days (temporary is fine).
6. Scopes: check **`repo`** (full control of private repositories).
7. Generate and **copy the token once** (you will not see it again).

Use that token in place of `YOUR_NEW_TOKEN` in the push command.

### After push

1. Open https://github.com/sipioapp/coffee-app-legal
2. **Settings** → **Pages**
3. **Build and deployment** → Source: **Deploy from a branch**
4. Branch: **main** / **/ (root)**
5. **Save**
6. Wait 1–3 minutes; pages appear at `https://sipioapp.github.io/coffee-app-legal/`

## Security note

Do not commit tokens to git. If a token is leaked, revoke it immediately under sipioapp → Settings → Developer settings.
