---
name: flight-price-monitoring
description: "Monitor flight prices and sanity-check Google Flights alerts against Oanh's airline, routing, and travel-pain preferences."
---

# Flight Price Monitoring

Use when Oanh asks to monitor flights, interpret Google Flights alerts, compare itineraries, or decide whether a fare is worth booking.

## Core approach

Hybrid monitoring:
- Oanh sets Google Flights alerts in her own logged-in browser/account.
- Mynah sanity-checks alerts and does periodic browser/web checks when useful.
- Do not recommend the cheapest fare if it is operationally miserable.

## Default quality filter

- Avoid Frontier and Southwest by default.
- Treat ultra-low-cost/basic-economy gotcha fares skeptically.
- Prefer reputable carriers and protected connections.
- For seniors/children, weight connection quality, total travel time, and departure/arrival times heavily.
- Avoid self-transfer unless Oanh explicitly accepts the risk.
- Avoid tight international connections and airport changes.

## Current trips to monitor

Read `projects/flight-price-monitoring.md` for live trip criteria.

Known 2026 trips:
- SEA to SRQ or MCO, 4 Aug, one-way, 2 adults + 1 child, economy, direct only, avoid Frontier/Southwest.
- SRQ to MAD, 7 Aug, arrive by 8 Aug, one-way, 4 adults + 1 child, economy. MCO/TPA acceptable but not ideal.
- MAD to SIN, 15 Aug, one-way, 2 adults + 1 child, economy.
- MAD to SRQ, 15 Aug, one-way, 2 senior adults, economy. Departure should be before MAD-SIN and ideally close in time.

## Output format

When reviewing a fare/alert:
- **Verdict:** ignore / watch / consider / book soon
- **Fare:** airline, route, price, passengers, cabin
- **Why it matters**
- **Pain points:** timing, connection, baggage/basic economy, airport, self-transfer
- **Better alternatives to check**
- **Recommended next action**

Keep it concise. Oanh wants useful signal, not a giant fare report.
