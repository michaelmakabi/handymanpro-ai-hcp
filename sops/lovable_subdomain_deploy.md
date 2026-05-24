# SOP — Deploy Lovable site to `handymanpro.ai-loren.com`

**Owner:** Loren AI ops
**Estimated time:** 10 minutes
**Prerequisites:** GoDaddy DNS already provisioned (done — see status below).

---

## Status — done by the build

- [x] GoDaddy A record: `handymanpro.ai-loren.com` → `185.158.133.1`

## Status — human action required

- [ ] Add custom domain in Lovable
- [ ] Verify SSL provisioning
- [ ] Hide Lovable badge
- [ ] Import the new `frontend/index.html` into the Lovable project

---

## Step 1 — Add custom domain in Lovable

1. Open the Lovable project: `https://lovable.dev/projects/e10a07e1-5cc8-4527-83e4-95652b69e2be`
2. Project Settings → Domain → Add custom domain
3. Enter: `handymanpro.ai-loren.com`
4. If Lovable asks for a TXT verification value, copy it and run:

```
godaddy_set_txt_record(
  domain="ai-loren.com",
  name="_lovable.handymanpro",
  value="lovable_verify=<TOKEN_FROM_LOVABLE>"
)
```

(Use the Loren AI MCP `godaddy_set_txt_record` tool — Mike has the credentials.)

5. Wait <5 min for SSL.

## Step 2 — Hide Lovable badge

Project Settings → Branding → toggle **Hide Lovable badge** to ON.

## Step 3 — Import the new design

The redesigned site lives at `frontend/index.html` in this repo.

Option A (recommended): paste the HTML into Lovable's code editor and let it render.

Option B: deploy `frontend/index.html` to GitHub Pages or Vercel and point the subdomain there instead. Trade-off — loses Lovable's visual editor.

## Step 4 — Verify

1. Open `https://handymanpro.ai-loren.com` in an incognito window.
2. Check: page loads, no Lovable badge, "Powered by LOREN AI" footer is present, phone number is `(754) 247-6766`.
3. Submit the lead form — verify it lands in GHL (after GHL sub-account is provisioned).

## Rollback

If anything goes wrong, the original preview URL still works: `https://preview--steelbuild-easy.lovable.app/`. No data loss.
