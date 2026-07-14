# Crisper — how to put this site live

Everything you need is in this folder (`crisperbeer-site`):

- `index.html` — the website (30 KB now, loads fast)
- `assets/` — the 6 photos (load separately + lazily)
- `favicon.png`, `favicon-32.png`, `apple-touch-icon.png` — the browser-tab / phone icon (red leaf)
- `og-image.jpg` — the preview card that shows when the link is shared on WhatsApp / Instagram / X
- keep every file where it is; the site references them by relative path.

**Recommended primary domain: `crisperbeer.com`** (clearest). We'll point that at the site and forward the other two to it.

---

## Fastest way live (≈10 minutes, no coding) — Netlify Drop

1. Go to **https://app.netlify.com/drop** and sign up free (Google login is fine).
2. **Drag this whole `crisperbeer-site` folder** onto the page.
   → It goes live in ~30 seconds at a temporary address like `random-name.netlify.app`. Open it, test the age gate on your phone.
3. Connect your domain: in Netlify → **Site → Domain management → Add a domain** → type `crisperbeer.com`.
4. Netlify will show you DNS records. Now open **Zoho → Domains → crisperbeer.com → DNS / Manage DNS** and add:
   - **A record** — Host: `@` → Value: `75.2.60.5`  *(Netlify's address)*
   - **CNAME** — Host: `www` → Value: `your-site-name.netlify.app`
5. Wait for DNS to update (usually minutes, up to a few hours). Netlify turns on **free HTTPS (the padlock)** automatically once it resolves.

Done — `crisperbeer.com` is your live site.

### Point the other two domains at it
In **Zoho**, for `drinkcrisper.com` and `borninthehimalayas.com`, use **Domain Forwarding / URL Forwarding** → forward to `https://crisperbeer.com` (choose permanent / 301). Now all three lead to the same place.

---

## Alternative (slightly faster in India): Cloudflare Pages
If you'd rather, `pages.cloudflare.com` → Create → Direct Upload → upload this folder → add `crisperbeer.com` as the custom domain. Cloudflare's network is a touch quicker for Indian visitors. Netlify Drop is simpler; either is fine.

---

## To update the site later
Change what you need, then just **drag the folder onto the same Netlify site again** (Deploys → drag to redeploy). That's it.

---

## Before you flip it on — 3 checks
1. **Verify the footer details** are current: the **FSSAI licence number** and the **XXX Spiritz address**. I used what was in your documents.
2. **Turn on age-restriction** anywhere else the brand lives (e.g. the Instagram account setting).
3. A quick **legal glance** is wise for a public alcohol site — including the "Born in the Himalayas" tagline vs the existing Woodsmen whiskey use (worth a trademark check).

*(The share-preview image and links inside `index.html` are set to `crisperbeer.com`. If you ever make a different domain the primary, open `index.html` and change the `crisperbeer.com` URLs near the top.)*
