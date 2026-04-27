# InvoLens

Tax invoice generator for Sabi Wabi Innovations LLP / Honey Touch — multi-user via Google Drive sync.

## Features

- 134-SKU product master with 4-column SKU search (Master / Amazon / Flipkart / Website / ASIN / FSN)
- Reverse-calculated GST from inclusive total (matches marketplace orders)
- Auto IGST vs CGST/SGST split based on buyer state
- Keyword-based HSN/GST overrides (e.g. mattress → HSN 9404, 12%)
- Customer database auto-built from invoices
- A4 print view matching existing invoice layout
- Replacement invoice mode
- Google Drive sync for multi-user access
- Full CSV export for invoices, customers, products

## Live URL

`https://sharpfarrier.github.io/involens/`

## File structure

```
involens/
├── index.html              ← rename involens_v1.html to index.html for GitHub Pages
├── products_seed.js        ← initial 134-product seed
└── README.md
```

## Drive sync setup

Already configured. Files created in: [Drive folder](https://drive.google.com/drive/folders/1v5oo7acB9o9JcbMSGkMrzXXsYMbh_XjP)

- `involens_settings.json`
- `involens_products.json`
- `involens_customers.json`
- `involens_invoices.json`

## Adding operators

1. Open the [Google Cloud Console OAuth consent screen](https://console.cloud.google.com/auth/audience?project=involens)
2. Add their Google account email under **Test users**
3. Right-click the [InvoLens Data folder](https://drive.google.com/drive/folders/1v5oo7acB9o9JcbMSGkMrzXXsYMbh_XjP) → Share → add as Editor
4. Send them the live URL — they sign in with their Google account

## Local testing

```bash
python3 -m http.server 8000
# Open http://localhost:8000/involens_v1.html
```

OAuth origin `http://localhost:8000` is whitelisted.
