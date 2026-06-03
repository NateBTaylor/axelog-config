# axelog-config

Remote config for the **AxeLog AI** iOS app — no database, no backend.

## `announcement.json` → the home-screen banner

The app fetches this file on launch and shows a dismissible banner on the Home
screen. **To change the banner, edit `announcement.json` and commit.** The new
banner appears the next time anyone opens the app.

```json
{
  "id": "welcome-2026-06",          // bump this to re-show to people who dismissed
  "active": true,                    // false = hide the banner (keep the file)
  "emoji": "🎸",                     // optional
  "title": "Welcome to AxeLog AI",   // optional
  "message": "…",                    // required
  "linkURL": null,                   // optional tap target (App Store, IG, blog…)
  "expiresAt": null                  // optional ISO-8601, e.g. "2026-07-01T00:00:00Z"
}
```

### Field notes
- **Hide it:** set `"active": false`.
- **New message:** change `"message"` **and bump `"id"`** so it re-shows even to
  users who dismissed the previous one.
- **Auto-expire:** set `"expiresAt"` and it hides itself after that date.
- **Tappable:** set `"linkURL"` — a gold chevron appears; tapping opens the URL.
- `emoji` and `title` are optional; a message-only banner works fine.

> Note: `raw.githubusercontent.com` has a ~5-minute CDN cache, so edits can take
> a few minutes to reach everyone.
