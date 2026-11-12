# ZARIS MACHINE À COUDRE

Website for a sewing-machine and ironing-equipment rental business (events, fashion shows, Fashion Week).
Based in France, delivery worldwide. Prices are in euros (€).

## Files

| File | What it is |
|---|---|
| `index.html` | Customer site: catalogue, product pages, rental basket, ordering through WhatsApp |
| `gestion.html` | Management page: quotes (devis), invoices (factures), purchase orders (BC), delivery notes (BL). Login required |
| `logo.jpg` | ZARIS logo |

Both pages are single self-contained HTML files. The logo is embedded in them, so they work without `logo.jpg`.

## Customer site (`index.html`)

- Catalogue of 11 items (machines, ironing, accessories, packs) with category filters.
- Click a picture, a name or **Voir la description** to open the product sheet (description, specifications, price per day, deposit).
- Rental basket: start date, number of days, shipping or pick-up in France, promo code `BIENVENUE` (-10 % on a first rental).
- Automatic discount by duration: 3-6 days -10 %, 7-29 days -20 %, 30 days or more -35 %.
- Orders are sent through WhatsApp (+33 6 10 72 62 94) from the product sheet, the basket, or the floating WhatsApp button.
- Shipping cost is "sur devis" because it depends on the destination.

## Management page (`gestion.html`)

- Four document types: **Devis**, **Facture**, **Bon de commande**, **Bon de livraison**, numbered automatically (DEV-2026-001, FAC-2026-001, ...).
- VAT 20 % or none, discount, refundable deposit, total written out in words (euros).
- Convert a quote into an invoice or a delivery note in one click.
- Saved-documents list with search and filter.
- The quote ends with a **COORDONNÉES BANCAIRES** block (contact details from the e-mail signature, not a bank account: no IBAN/BIC yet).
- Company details (ICE, RC, IF, patente, RIB) are filled in under *Informations de l'entreprise*.
- Login: username `ndey` (password given separately).
- Send a document: **Envoyer sur WhatsApp** (opens a chat with the client if a phone number is entered; numbers starting with `0` are treated as French `+33`) or **Copier le texte**.
- **Télécharger** produces an HTML file; open it and use *Imprimer / Enregistrer en PDF*.

## Settings

Open `index.html` in a text editor and edit the `CFG` block at the top of the script:

```js
const CFG={
  wa:'33610726294',               // WhatsApp number, international format, no +
  phoneShow:'+33 6 10 72 62 94',  // number displayed on the site
  deliveryFee:0,                  // 0 = shipping quoted separately
  promoCode:'BIENVENUE', promoRate:0.10
};
```

Products, prices (€ per day) and deposits are in the `PRODUCTS` list just below. Long descriptions and specifications are in `DETAILS`.
Prices and deposits are estimates until the owner confirms them.

## Storage

- On Claude (published artifacts), saved documents go to the artifact database and are readable only by the owner and invited Editors.
- Outside Claude (these files opened in a browser or hosted elsewhere), `gestion.html` stores documents in that browser only. They are not shared between devices.

## Security

The login hides the management page from ordinary visitors. It runs in the browser, so it is not real server-side security.
Do not put sensitive data (full bank details, ID numbers) in the documents until a proper authentication system is added.

## Still to do

- Confirm prices and deposits.
- Add product photos (currently icons).
- Add the models (brand and reference) of each machine.
- Add a second account for the management page.
- Add IBAN/BIC to the quote if wanted.

## Live versions (private until shared)

- Customer site: https://claude.ai/artifact/NrN49DfMDY4Y474VMkpcw1
- Management page: https://claude.ai/artifact/9QWozDYYpMmLs19EyXN2AQ
