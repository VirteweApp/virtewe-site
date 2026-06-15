# App deep links on www.virtewe.com

The marketing site (`virtewe-site`) is hosted on Render at `www.virtewe.com`.
The React app (`virtewe-web`) is hosted on Vercel at `app.virtewe.com`.

Direct paths such as `/admin` are **not** part of this static site. Without a
redirect rule, Render returns a plain-text `Not Found`.

## Admin dashboard URL

Use:

```text
https://app.virtewe.com/admin
```

## Render redirect rule

If `render.yaml` is not linked to the Render service, add this rule in the
Render dashboard (**Redirects/Rewrites**):

| Source | Destination | Action |
|--------|-------------|--------|
| `/*` | `https://app.virtewe.com/*` | Redirect |

Render skips the rule when a static file exists (for example `/privacy.html`),
so marketing pages keep working.
