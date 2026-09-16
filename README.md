# OmniTools Platform Architecture Guide

Welcome! This architecture was specially designed for a **solo builder with zero IT/coding experience** using AI to build and scale a high-traffic tools portal on a **$0 to $3/month budget**.

---

## 1. Project Directory Structure

```text
omnitools-platform/
│
├── index.html          <-- The Main Portal (Search bar, dark mode, dynamic category filters)
├── tools.json          <-- THE MASTER REGISTRY (The ONLY file you edit to add/remove tools)
│
└── tools/              <-- Modular Lego Folders (Each tool is 100% independent)
    ├── image-compressor/
    │   └── index.html
    ├── loan-emi-calculator/
    │   └── index.html
    ├── age-calculator/
    │   └── index.html
    ├── discount-calculator/
    │   └── index.html
    ├── word-counter/
    │   └── index.html
    ├── qr-generator/
    │   └── index.html
    └── password-generator/
        └── index.html
```

---

## 2. How to Add a New Tool in 3 Simple Steps

Whenever you want to add a new tool (e.g., `tip-calculator`):

### Step 1: Create a New Folder
Create a folder inside `tools/` with your tool's name:
`tools/tip-calculator/index.html`

### Step 2: Paste the Code
Ask your AI to write the tool and paste the code into that new `index.html`.

### Step 3: Add to `tools.json`
Open `tools.json` and append your tool entry:
```json
{
  "id": "tip-calculator",
  "name": "Tip & Bill Splitter",
  "category": "Calculators",
  "icon": "💵",
  "description": "Split restaurant bills and calculate tip per person.",
  "keywords": ["tip", "bill", "split", "restaurant", "dining"],
  "badge": "New"
}
```
**That's it!** The homepage will automatically display the new card, update the category counts, and make it instantly searchable.

---

## 3. How to Remove a Tool
1. Delete its folder from `tools/`.
2. Delete its entry from `tools.json`.

---

## 4. How to Host 100% Free on Cloudflare Pages or GitHub Pages

Because there is **no database and no backend server required**:
1. Push this folder to a new GitHub repository.
2. Go to **Cloudflare Pages** (or GitHub Pages Settings).
3. Connect your repository and click **Deploy**.
4. Your website is live worldwide with free SSL and infinite bandwidth.
