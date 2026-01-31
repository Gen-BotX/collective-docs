# Collective GitBook — Structure Guide

This folder contains all the docs content for GitBook. Here's how to set it up:

## GitBook Setup

1. Go to [gitbook.com](https://gitbook.com) and create an account
2. Create a new Space (your docs site)
3. You can either:
   - **Manual:** Create pages in GitBook and copy/paste content from these files
   - **GitHub Sync:** Connect to a GitHub repo and GitBook will sync automatically

## Recommended Page Structure

```
📁 Collective Docs (Space)
│
├── Welcome                         ← 01-welcome.md
├── How It Works                    ← 02-how-it-works.md
│
├── 📁 For Funders
│   ├── Getting Started             ← 03-for-funders/01-getting-started.md
│   ├── How Returns Work            ← 03-for-funders/02-returns.md
│   ├── Withdrawals                 ← 03-for-funders/03-withdrawals.md
│   └── Risks                       ← 03-for-funders/04-risks.md
│
├── 📁 Vendors
│   ├── Overview                    ← 04-vendors/01-overview.md
│   └── Collective Vendor           ← 04-vendors/02-collective-vendor.md
│
├── 📁 Protocol
│   ├── Vault Mechanics             ← 05-protocol/01-vault-mechanics.md
│   ├── Fee Structure               ← 05-protocol/02-fees.md
│   ├── Transparency                ← 05-protocol/03-transparency.md
│   └── Smart Contracts             ← 05-protocol/04-contracts.md
│
├── 📁 Resources
│   ├── FAQ                         ← 06-resources/01-faq.md
│   └── Links                       ← 06-resources/02-links.md
│
└── 📁 Legal
    ├── Terms of Service            ← 07-legal/01-terms.md
    └── Privacy Policy              ← 07-legal/02-privacy.md
```

## Placeholders to Fill In

Search for `[TBD]` or `[X]` in the docs — these are placeholders that need your input:

- **Vendor name** (your brother's name or alias)
- **Contract addresses** (once deployed)
- **HyperEVM network details** (RPC URL, Chain ID)
- **Operating cost caps** (% of vault)
- **Platform fee** (if any)
- **Bug bounty amounts**
- **Discord/Telegram links**
- **Email addresses**
- **Launch dates**
- **Legal jurisdiction**

## Customization

Feel free to edit any of these docs. They're a starting point — make them yours.

Key things you might want to change:
- Tone (more casual? more formal?)
- Specific numbers (minimums, caps, fees)
- Your brother's bio and track record details
- Risk emphasis (more aggressive? more cautious?)

## Images & Branding

GitBook supports images. You'll want to add:
- Logo in the header
- Diagrams for "How It Works"
- Vendor photos (optional)
- Card examples / portfolio highlights

## After Setup

Once your GitBook is live:
1. Set a custom domain (docs.collective.markets)
2. Link from your main site
3. Add to footer/nav on collective.markets
