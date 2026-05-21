# Flight Price Monitoring

_Last updated: 2026-05-21_

## General monitoring preference

Hybrid approach:
- Use Google Flights alerts for broad market movement.
- Mynah sanity-checks so alerts for undesirable/crappy airlines do not trigger bad recommendations.
- Flag reasonable fares separately from cheapest-but-bad fares.

Current status:
- Oanh has set Google Flights alerts in her own browser/account.
- Chromium is installed on the OpenClaw host and browser doctor detects it.
- Browser `open` still times out even after gateway restart; browser plugin can see Chromium but is not launching pages reliably yet. Need further browser-plugin diagnosis later.
- In the meantime, use Google Flights alert emails/screenshots plus manual web sanity checks.

## Quality filters

- Avoid Frontier and Southwest by default.
- Treat ultra-low-cost/basic-carrier fares skeptically.
- For domestic US direct flights, prefer Alaska or Delta where available.
- For long-haul/international, prioritize sane routing, protected connections, and total travel pain — not just headline price.

## Trip 1: SEA to SRQ or MCO, 4 Aug 2026

Request from Oanh:
- Origin: Seattle SEA.
- Destination: Sarasota SRQ or Orlando MCO.
- Date: 4 Aug 2026.
- One way.
- 2 adults, 1 child.
- Economy.
- Direct flight only.
- Avoid Frontier and Southwest.

Initial route sanity:
- SEA-MCO appears to have nonstop service, likely Alaska Airlines and Delta Air Lines.
- SEA-SRQ nonstop appears unlikely/not obvious from quick search; likely requires connection and may violate direct-only constraint.

Watch criteria:
- Best reasonable nonstop SEA-MCO fare for 3 passengers.
- Ignore/flag Frontier/Southwest or painful basic fares.
- If SRQ has no nonstop, do not treat connecting SRQ itineraries as valid unless Oanh relaxes direct-only.

## Trip 2: SRQ to MAD, depart 7 Aug 2026, arrive by 8 Aug 2026

Request from Oanh:
- Origin: Sarasota SRQ.
- Destination: Madrid MAD.
- Depart: 7 Aug 2026.
- Must reach Madrid by 8 Aug 2026.
- One way.
- 4 adults, 1 child.
- Economy.

Open assumptions / questions:
- Direct from SRQ to MAD is almost certainly not available; assume connections are acceptable unless Oanh says otherwise.
- Nearby airports: MCO and TPA are acceptable but not ideal. Do not assume MIA/FLL are acceptable unless Oanh says so.
- Need to know airline preferences/avoid list for transatlantic routes.

Watch criteria draft:
- Prefer SRQ origin if pricing/routing is reasonable.
- Compare MCO and TPA as acceptable fallbacks, not first choice.
- Prefer sane one-stop or two-stop protected itineraries.
- Avoid self-transfer unless huge savings and Oanh explicitly accepts the risk.
- Avoid very tight international connections and overnight airport pain unless necessary.

## Trip 3: MAD to SIN, 15 Aug 2026

Request from Oanh:
- Origin: Madrid MAD.
- Destination: Singapore SIN.
- Date: 15 Aug 2026.
- One way.
- 2 adults, 1 child.
- Economy.

Coordination requirement:
- Should be coordinated with Trip 4 (MAD to SRQ for 2 senior adults) on the same date.
- Best if departure times are close together.
- MAD-SRQ departure should be before MAD-SIN departure time.

Watch criteria draft:
- Prefer sane one-stop itineraries with reputable long-haul carriers.
- Avoid painful overnight layovers or self-transfer unless explicitly accepted.
- Since traveling with child, weigh total travel time and connection quality heavily.

## Trip 4: MAD to SRQ, 15 Aug 2026

Request from Oanh:
- Origin: Madrid MAD.
- Destination: Sarasota SRQ.
- Date: 15 Aug 2026.
- One way.
- 2 adults, seniors.
- Economy.

Coordination requirement:
- Departure should be before the MAD-SIN flight departure.
- Departure time should ideally be close to the MAD-SIN departure so everyone can go to airport together / similar window.

Airport flexibility:
- Destination should be SRQ unless Oanh later allows nearby airports.

Watch criteria draft:
- Prioritize sane/protected connections and senior-friendly routing over absolute cheapest fare.
- Avoid tight connections, self-transfer, and airport changes.
- Prefer reasonable departure time from MAD before the MAD-SIN flight.
