# Music by Caruso — website

Live site: **https://musicbycaruso.com**

Single-page website for Frank Caruso's live music business in Central Florida. The whole site is one file (`index.html`) — embedded photo, embedded fonts (via Google Fonts), no build step, no dependencies.

---

## How it's hosted

| Piece     | Service          | Cost  |
|-----------|------------------|-------|
| Registrar | GoDaddy          | annual |
| DNS       | Cloudflare       | free  |
| Hosting   | Cloudflare Pages | free  |
| SSL       | Cloudflare (auto)| free  |

The site auto-deploys from this repo's `main` branch. Any commit to `main` goes live globally on Cloudflare's CDN in ~30 seconds.

---

## Editing the site

All editable text in `index.html` is marked with `EDIT:` comments. There are two ways to make a change.

### The easy way — in your browser, no install needed

1. Go to this repo on **github.com**
2. Click `index.html`
3. Click the **pencil icon** at the top-right of the file
4. Press **Ctrl+F** (or **Cmd+F** on Mac) and search for **EDIT**
5. Find the section, change the words *between* the tags — leave the tags alone
6. Scroll to the bottom, write a short note (e.g. "Updated phone number"), click **Commit changes**
7. ~30 seconds later the change is live on musicbycaruso.com

### The local way — for bigger changes

```bash
git clone https://github.com/YOUR-USERNAME/musicbycaruso-site.git
cd musicbycaruso-site
# edit index.html in your editor
open index.html     # preview in browser
git add index.html
git commit -m "Update song list"
git push
```

---

## Common edits

**Change the phone number**
Search for `407` — it appears in the contact row, the footer, and inside the `tel:` link. Update all three.

**Change the email**
Search for `fecaruso@me.com` — appears in the contact row, the footer, the booking form `mailto:`, and the SEO meta tags.

**Add or remove a song**
Search for `EDIT THE SONG LIST`. To add a song: copy a line like `<li>Brown Eyed Girl</li>`, paste it below, change the song name. To remove: delete the whole `<li>...</li>` line.

**Update Frank's bio**
Search for `EDIT: Frank's story`.

**Change the headline tagline**
Search for `EDIT: the headline tagline`.

**Swap Frank's photo**
The photo is embedded as a data URI to keep everything in one file. To replace it: send the new photo to Giorgio and he'll re-embed it. Or, do it yourself by uploading the photo to the repo and changing the `<img src="...">` line on the hero photo to point to the new file path.

---

## Future upgrades (when you want them)

**Real booking form** — currently the form opens the visitor's email app via `mailto:`. To receive submissions directly in an inbox:
- **Easiest:** Formspree — free up to 50 submissions/month, one HTML attribute change
- **Cloudflare-native:** a Pages Function forwarding to Resend, ~20 lines of code, still free

**Visual editor for Frank** — Decap CMS adds an admin page (`/admin`) where Frank edits via form fields instead of HTML. One-time setup, sits on top of this same stack, free.

**Branded email** — `frank@musicbycaruso.com` instead of `fecaruso@me.com`:
- **Free option:** Cloudflare Email Routing forwards mail at the domain to any existing inbox
- **Full mailbox:** Google Workspace or similar (paid)

**Performance video** — search for `TO ADD A VIDEO` in `index.html` — instructions are inline.

---

## Files in this repo

- `index.html` — the entire website (~110 KB, includes Frank's photo)
- `README.md` — this file
- `.gitignore` — keeps OS and editor junk out of commits
