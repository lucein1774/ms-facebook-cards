# Major Surplus & Survival — Facebook Post Card Generator

A hosted tool for generating branded, ready-to-post Facebook images from product specials emails. Each campaign lives as its own HTML file, accessible from any browser with one-click PNG download per card.

---

## Live Site

**[lucein1774.github.io/ms-facebook-cards](https://lucein1774.github.io/ms-facebook-cards)**

---

## How It Works

Each HTML file is a self-contained post card generator for one email campaign. Open it in a browser to:

- View all product cards for that campaign
- Edit UTM parameters and apply them to all links at once
- Copy the product link + UTM for each card
- Download each card as a PNG ready to upload to Facebook

No login, no app, no subscription. Everything runs in the browser.

---

## File Structure

```
ms-facebook-cards/
├── index.html                        ← Campaign dashboard (start here)
├── README.md                         ← This file
│
├── mountain-house-specials.html      ← Mountain House / June 2026
├── voodoo-tactical-[campaign].html   ← Voodoo Tactical campaigns
└── [brand]-[campaign-name].html      ← Future campaigns
```

### Naming Convention

Use lowercase with hyphens, brand first:

```
major-surplus-[campaign-name]-[month]-[year].html
voodoo-tactical-[campaign-name]-[month]-[year].html
```

Examples:
```
major-surplus-mountain-house-june-2026.html
voodoo-tactical-summer-drop-june-2026.html
major-outdoors-camping-gear-july-2026.html
```

---

## Adding a New Campaign

### Step 1 — Generate the cards
Upload the specials email (HTML export, PNG screenshot, or PDF) to Claude in the `ms-facebook-cards` project. Specify the brand and account type. Claude reads every product and generates a post card HTML file.

### Step 2 — Upload to GitHub
- Go to your repository on github.com
- Click **Add file** → **Upload files**
- Upload the generated HTML file with the correct naming convention
- Click **Commit changes**

### Step 3 — Add to the index
- Edit `index.html`
- Add a new campaign card with the brand, campaign name, date, and link
- Commit the change

The new campaign is live at its URL within ~60 seconds.

---

## UTM Parameters

Each card file has a UTM editor at the top. Default values:

| Parameter | Default |
|---|---|
| `utm_source` | `facebook` |
| `utm_medium` | `social` |
| `utm_campaign` | Set per campaign (e.g. `mountain-house-specials`) |
| `utm_content` | Set per card automatically (e.g. `beef-stroganoff`) |

Click **Apply to All Cards** after editing to update every link in the file. Individual links can also be edited directly in each card.

---

## Downloading Cards as PNG

1. Open the campaign file in **Google Chrome** (recommended for best rendering)
2. Wait for all product images to load
3. Click **↓ Download PNG** under any card
4. The file saves to your Downloads folder named `major-surplus-[product].png`
5. Upload directly to Facebook — no editing needed

> **Tip:** If a product image doesn't load (CDN restriction), scroll to that card and wait a moment before downloading. The PNG captures whatever is visible in the browser.

---

## Brands

### Major Surplus & Survival
- Tone: Rugged, patriotic, deals-focused, no-nonsense
- Accent color: `#c41e1e` (red)
- Bonus offer accent: `#e86b00` (orange)
- Target audience: Outdoor enthusiasts, preppers, military surplus collectors, tactical gear users

### Voodoo Tactical
- Tone: Professional, tactical, precision-focused, mission-ready
- Target audience: Law enforcement, military, security professionals, tactical enthusiasts
- *(Campaigns coming soon)*

---

## Technical Notes

- All logos and embedded images (e.g. water filter) are base64-encoded directly in the HTML — no external dependencies
- Product images load from the store's CDN and require an internet connection
- PNG export uses [html2canvas](https://html2canvas.hertzen.com/) at 2× scale for high-resolution output
- Files are self-contained and work offline except for CDN-hosted product images

---

## Project History

Built with Claude (Anthropic) in the `ms-facebook-cards` project. To make changes or generate new campaigns, open that project in Claude and upload the new specials email.
