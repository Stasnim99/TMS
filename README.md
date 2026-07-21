# TMS

A sample Power BI report (`TMS.pbix`) simulating a Transportation Management System (TMS) dashboard for a logistics/freight operation. All data is synthetic and built for portfolio demonstration purposes only — carrier names, dollar figures, and shipment details are not real.

## Contents

| File | Description |
|---|---|
| `TMS.pbix` | The Power BI Desktop report — three dashboard pages plus a navigation menu, described below. |
| `Production/tms_TransportationLoadLevels.csv` | Load-level fact table: one row per shipment, with division, origin/destination, carrier, mode, service level, weight, and the freight/accessorial/total/benchmark cost breakdown. Drives most of the Division Summary and Carrier Footprint visuals. |
| `Production/tms_StopLevelDetails.csv` | Stop-by-stop detail for each load (pickup and delivery stops) — location, distance/duration from the previous stop, planned quantities, and appointment vs. actual arrival/departure times. |
| `Production/tms_InboundDetails.csv` | Inbound shipment tracking detail — carrier, shipper/consignee, pickup and delivery dates, weight, miles, rate, and total charges per load. |
| `Production/tms_ReferenceTableLaneOwner.csv` | Lookup table mapping each division/lane ownership key to the user responsible for it. |

## Report pages

### Main Menu
The landing page. It gives a one-click jump to each of the three views below (Division Summary, Compliance Reporting, Carrier Footprint).

### Division Summary
![Division Summary](screenshots/division-summary.png)

Division-level performance overview. KPI cards across the top summarize Total Cost, Load Count, Total Weight, Miles, Fill Rate %, and Cost per Lb, alongside a "Cost per Pound Diff." card comparing actual cost/lb to a target goal. Below that, a trendline tracks Cost per Pound day-over-day against the same metric from the prior week, and a scatter plot plus breakdown table compare cost and weight across each division (DIV1–DIV5). Slicers on the left filter everything by Division ID and Date.

### Compliance Reporting
![Compliance Reporting](screenshots/compliance-reporting.png)

Audits carrier trips against expected/contracted rates. The main table lists every trip with origin, destination, the user who booked it, carrier, rate source (Spot vs. Contract), and the resulting compliance cost (the $ variance from the benchmark rate). A bar chart and table below roll that variance up by user, making it easy to see who is booking the most out-of-compliance freight. Slicers filter by origin/destination city and state and by user.

### Carrier Footprint
![Carrier Footprint](screenshots/carrier-footprint.png)

Carrier-level spend and volume tracking. KPI cards show Shipments MTD/QTD/YTD, Load Count, and Benchmark Total. The main table breaks out total cost, week-over-week spend change (% and $), benchmark total, and load count per carrier. Two toggle buttons ("WoW Spend By Carrier" / "Load By Carrier") switch the charts below between top-5 and bottom-5 carriers by load volume. Slicers on the left filter by division, origin/destination, user, and carrier.
