# Fruit Group Buy Automation

_Last updated: 2026-05-22_

## Context

Oanh coordinates a weekly neighborhood fruit group buy from a wholesaler.

Current workflow:
1. Every Friday, ask wholesaler for the fruit availability/price list.
2. Copy/paste the list into a Google Sheet.
3. Neighbors enter orders.
4. On Saturday, review orders and adjust to fill full boxes.
5. Send final order to wholesaler.
6. Fruit is delivered and distributed.
7. Neighbors pay Oanh.
8. Payment reconciliation is painful because people do not always pay promptly, and Oanh may need to review nearly two months of transactions at once.

## Spreadsheet access

Google Sheet URL:
- https://docs.google.com/spreadsheets/d/128HmQvIfyZzb3iXgsooUj9aCygMpUo-UMefCR0Knqac/edit

Spreadsheet ID:
- `128HmQvIfyZzb3iXgsooUj9aCygMpUo-UMefCR0Knqac`

Google Sheet title:
- `Fruit sharing`

Access method:
- Google Sheets API via service account.
- Service account key is stored on VM only at `~/.openclaw/secrets/google-sheets-fruit-sa.json`.
- Service account email: `openclaw-fruit-sheets@openclaw-bot-496808.iam.gserviceaccount.com`.
- Oanh shared the fruit spreadsheet with this service account as Editor.
- Read-only test succeeded on 2026-05-22: fetched spreadsheet metadata and sample ranges from `Template (duplicate)` and `15 May - Oanh`.
- Write test succeeded on 2026-05-22: created scratch tab `Mynah test` and wrote/read harmless sample data in `A1:C3`.

Security notes:
- Do not commit service account JSON or raw neighbor/payment data to GitHub.
- Prefer summaries and anonymized notes in repo.
- For writes, test in a copied/scratch tab first.

## Spreadsheet observed from API/screenshots

Visible tabs include:
- `Read me first if you're new`
- `Fruit ferry rotas`
- `Template (duplicate)` — sheet ID `70299840`, 1108x61
- weekly tabs such as `15 May - Oanh`, `8 May - Oanh`, `1 May -Oanh`, etc.

Sample structure from `15 May - Oanh`:
- Row 1: group header such as `Faber Crest`, FC count.
- Row 2: quantity/cost breakdown header areas.
- Row 3: item columns:
  - A `Index`
  - B `Description`
  - C `Box price`
  - D `Kgs/pcs per box`
  - E `Unit`
  - F `$ per kg/pc`
  - G onward: neighbor order quantity columns (e.g. Eunyoung, Georgina, Giulia, Maggie, Oanh, Xiaoxuan, Yeo Min)
  - later columns: cost breakdown per person, increase/decrease to full box, boxes ordered, payment/refund areas.

Example item rows from `15 May - Oanh`:
- `Us peaches 44 pcs $110` → box price $110, 44 pc, $2.50/pc.
- `Blue jay oranges 56 pcs $55` → box price $55, 56 pc, $0.98/pc.
- `Lychee 9 kgs $35` → box price $35, 9 kg, $3.89/kg.

## What Mynah could help with

### Weekly sheet update

- Parse wholesaler WhatsApp/email price list.
- Clean item names, units, box prices, and quantities.
- Create/update the weekly Google Sheet tab from a template.
- Preserve formulas, participant columns, and payment rows.

### Box-fill checking

- After neighbors enter orders, calculate whether totals fill full boxes.
- Flag rows needing increase/decrease.
- Suggest minimal adjustments.
- Generate final wholesaler order message.

### Payment reconciliation

- Track expected amount owed per person per week.
- Track paid/unpaid status.
- Summarize who owes what across weeks.
- Reconcile against payment screenshots/exports if Oanh explicitly provides data.
- Generate polite reminder messages.

## Recommended implementation plan

1. **Read-only mapping** — inspect template and one recent completed tab to map formulas/sections.
2. **Scratch-tab write test** — duplicate template or create a small `Mynah test` tab and write harmless sample values.
3. **Wholesaler-list parser** — Oanh sends weekly list; Mynah parses into rows: description, box price, units per box, unit, price/unit.
4. **Weekly tab creation** — duplicate template, rename to date, fill item rows.
5. **Box-fill checker** — after orders close, read totals and suggest adjustments/final wholesaler order.
6. **Payment helper** — later; requires careful handling of names/payment evidence.

## Potential bot/service insight

This is another concrete example of a practical AI assistant for non-technical recurring operations:
- messy inbound list
- structured spreadsheet
- group coordination
- reconciliation
- reminder messages

Useful as a case-study pattern for small-business / community admin automation.
