# 🚐 School Van Profit Optimizer

A decision-support tool for small school-transport operators in Sri Lanka. It helps you work out how to run, and possibly convert, a school van most profitably, without simply assuming that more seats means more profit.

**Live app:** https://aakifahmedd.github.io/school-van-optimizer/

## What it does

- **Dashboard:** monthly revenue, costs and profit, active students, seats filled, profit per vehicle-hour, average route time, break-even students, and a Sankey diagram showing where fees come from (by pickup area) and where the money goes (fuel, maintenance, driver, insurance, other costs, profit).
- **Vehicle:** editable specs, costs and engineering assumptions. Includes a 1990s Nissan Caravan/Urvan-style preset, marked as an assumption.
- **Students:** add and edit students with pickup area, school, fee, times and active status.
- **Distances:** no map integration — enter each real-world leg once as a From/To pair with its distance in km (e.g. "Depot to Obeysekarapura: 1 km"), the way you'd read it off Google Maps. The app warns you when a leg used by an active student is missing, since a missing distance is otherwise silently treated as 0 km.
- **Routes:** groups students into routes with a nearest-neighbour heuristic and shows students, revenue, km, hours, cost, profit per student and per hour for each route. Underused routes are highlighted.
- **Capacity:** an interactive top-down van layout (14 / 16 / 18 / 20+ or custom seats) with checks for space, payload, aisle, door and emergency-exit clearance. It also shows the marginal profit of each extra seat.
- **Scenarios:** compare seat configurations side by side on the same students and routes, with conversion cost and payback.
- **Economics:** break-even analysis, a "what if" panel and a sensitivity table showing which variables matter most.

## Important notes

- All results are **estimates**. The routing is a simple heuristic, not a mathematically optimal solution.
- Vehicle specs, seat-space assumptions and fuel prices are **editable inputs**, not verified data. The legal seat limit is a field you fill in from your own registration documents; the app cannot determine it.
- Minimum aisle, door and exit clearance are treated as hard limits, and layouts that break them are flagged as not feasible.
- Assumed effects of extra seats (0.6% worse fuel economy and 1.5% higher maintenance per added seat) are rough guesses; adjust them to your own experience.
- If you drive the van yourself with no paid driver, set Driver cost to 0 — profit then excludes any wage for your own time.

## Data and privacy

Everything runs in the browser. Data is saved in `localStorage` on your own device and is never uploaded. Use **Vehicle → Export / Import** to back up or move data, and **Reset demo data** to start over.

## Run locally

It is a single self-contained file with no dependencies. Download `index.html` and open it in any modern browser.

## Tech

Plain HTML, CSS and JavaScript, with charts, the Sankey diagram and the van layout drawn as inline SVG. Responsive for phone, tablet and desktop.
