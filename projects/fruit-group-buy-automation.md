# Fruit Group Buy Automation

_Last updated: 2026-05-22_

## Context

Oanh coordinates a weekly neighborhood fruit group buy from a wholesaler.

The group is split across two condos, Faber Crest and Clementi Park. They order together because the original group split as people moved, then more people joined. Final orders are sent to the seller as a split order by condo, while trying to minimize fruit transfers between condos because the seller only delivers whole boxes. Each week Oanh asks for a volunteer to handle the fruit exchange / bring remaining fruits to the right place.

Free delivery minimum: each condo delivery block needs at least $200. Sometimes this overrides the otherwise-optimal split logic: Oanh may allocate extra boxes to a condo to hit the free-delivery threshold, then arrange fruit transfer afterward.

Observed final seller-order format from 15 May example: greeting, then one delivery block per condo with condo/contact details, each item as `<box count>x <description>`, then `Total N ctns`, then optional delivery note. In that example Faber Crest had 11 cartons and Clementi Park had 8 cartons. Final seller orders must always include each condo's address, contact phone number, and contact name. Raw contact details are stored only in the local private template at `private/fruit-seller-order-template.md`, which is gitignored; do not commit them.

Fruit exchange list: after whole boxes are assigned to each condo for delivery, Oanh sends a short list of the loose quantities that must be ferried to the other condo so final distribution matches individual orders. Format is usually `For FC` and `For CP` sections, with quantities like `22 peaches`, `3 pkts grapes`, `1.5kg cherries`. These are not seller order lines; they are transfer instructions for the volunteer.

Delivery-risk note: the seller has previously switched the two condo delivery orders (FC received CP's fruit and vice versa), causing a Saturday-afternoon scramble. Future final-order messages should make the condo blocks very visually clear and may need a post-order confirmation/check that FC/CP delivery allocation is understood.

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
- Never delete any spreadsheet tab unless Oanh explicitly requests or approves that specific deletion.

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
- For kg boxes, wholesaler quotes are usually gross weight. Enter a slightly reduced usable quantity when past orders imply it (e.g. 3 kg tomatoes → 2.5 kg, 5 kg sweet potato/cherry → 4.5–4.6 kg, 10 kg guava → 9.5 kg). Bias conservative: people are happy with extra fruit, grumpy if they receive less than stated.
- If the seller runs out of stock after orders are collected, leave the item row in the list but delete/clear people's quantities for that item so totals stay correct and nobody is charged for unavailable fruit.
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
5. **Payment helper** — when Oanh sends payment confirmations, identify payer/group, compare paid amount against expected total, and tick the relevant `Paid` checkbox.
6. **Order finalization learning/trial** — Oanh will keep doing final order judgement calls for now. After observing a couple of order finalizations, trial partial automation/suggestions carefully; there is no fixed algorithm yet.

## Potential bot/service insight

This is another concrete example of a practical AI assistant for non-technical recurring operations:
- messy inbound list
- structured spreadsheet
- group coordination
- reconciliation
- reminder messages

Useful as a case-study pattern for small-business / community admin automation.
