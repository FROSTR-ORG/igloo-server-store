## Igloo Server – Umbrel Community Store

This store hosts the Umbrel package for **Igloo Server**, the multi-user FROSTR signing server with an embedded relay and guided onboarding.

### How to install on Umbrel
1. In Umbrel, add a community store using this repo URL: `https://github.com/frostr-org/igloo-server-store`.
2. Install **Igloo Server** from the newly added store.
3. The app starts on port `8002` (Tor is supported).

### First-run / onboarding flow
- Umbrel auto-sets `ADMIN_SECRET` and enables `SKIP_ADMIN_SECRET_VALIDATION`, so you **skip the admin-secret screen** and land directly on account creation.
- The Admin Secret is still stored and surfaced in the **Configure** page (masked by default) for API calls or external clients.
- After creating your admin user, configure signer credentials on the Configure tab, then use the Signer tab.

### Environment defaults (Umbrel)
- `AUTH_ENABLED=true`
- `SKIP_ADMIN_SECRET_VALIDATION=true`
- `ADMIN_SECRET` comes from Umbrel’s generated app password
- `DB_PATH=/app/data/igloo.db`
- `HOST_PORT=8002`
- `ALLOWED_ORIGINS` prefilled for `umbrel.local` (HTTP/HTTPS)

### Image tag
The store tracks the rolling tag `ghcr.io/frostr-org/igloo-server:umbrel-dev`. When a new build is published, reinstall the app (or `docker pull` the tag) to pick it up. Hard-refresh your browser if the UI looks stale.
