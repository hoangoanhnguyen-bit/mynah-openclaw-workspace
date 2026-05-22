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

## Spreadsheet observed from screenshots

Google Sheet title: Fruit sharing.

Visible structure:
- Weekly tabs, e.g. `15 May - Oanh`, `8 May - Oanh`, `1 May - Oanh`, etc.
- Sections include neighborhood/group areas such as Clementi Park and combined totals.
- Item rows include fruit description, box price, kg/pc/box, unit, price per kg/pc, individual order columns, total price, increase/decrease to full box, number of boxes ordered.
- Payment area includes totals, collected, paid checkboxes, refunds/owed.

## What Mynah could help with

### Weekly sheet update

- Parse wholesaler WhatsApp/email price list.
- Clean item names, units, box prices, and quantities.
- Create or update the weekly Google Sheet tab from a template.
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
- Reconcile against payment screenshots/exports if Oanh provides data.
- Generate polite reminder messages.

## Access needed

Current OpenClaw has Google Calendar OAuth only, not Google Sheets write access.

Options:
1. Google Sheets API OAuth/client setup for this VM.
2. Service account shared into the fruit Google Sheet.
3. Browser automation using Oanh's logged-in browser, if a local/browser node is available.
4. Manual mode: Oanh exports/downloads CSV or shares copied data; Mynah returns paste-ready tables/messages.

Recommended setup:
- Use a Google service account or Sheets OAuth with least privilege.
- Share only the `Fruit sharing` sheet with the integration account.
- Start with one low-risk action: parse the wholesaler list into a paste-ready table before allowing direct writes.

## Safety / privacy

- Do not access bank/payment data unless Oanh explicitly provides it for reconciliation.
- Prefer payment summaries over raw transaction storage.
- Keep neighbor contact/payment details out of GitHub unless anonymized.

## Potential bot/service insight

This is another concrete example of a practical AI assistant for non-technical recurring operations:
- messy inbound list
- structured spreadsheet
- group coordination
- reconciliation
- reminder messages

Useful as a case-study pattern for small-business / community admin automation.
