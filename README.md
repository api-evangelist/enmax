# ENMAX (enmax)

ENMAX Corporation is the Calgary-based energy company owned outright by The City of Calgary, describing itself on its own about page as "a regulated wires company, a competitive power generator and an energy retailer" operating "across Alberta and Maine." It spans three tiers of the value chain at once: ENMAX Power owns and operates the regulated electricity distribution and transmission system inside Calgary, ENMAX Energy generates power and sells electricity and natural gas into Alberta's deregulated retail market under the Easymax brand, and Versant Power — acquired from Emera in 2020 — is the transmission and distribution utility for northern and eastern Maine. Its API posture is the exact inverse of the Ontario utilities it is usually compared to, and the inversion is the finding. No consumer energy data mandate binds ENMAX anywhere it operates: Alberta has no Green Button regulation, Ontario's O. Reg. 633/21 does not reach across the provincial border, Canada has no national equivalent, and Maine imposes no Green Button obligation on Versant Power. Unmandated, ENMAX built nothing — its own support documentation states plainly that the Energy Insights usage view inside a customer's Easymax account "is view-only within your online account and can't be exported at this time," which is a harder closure than most: not merely no API, but no CSV, no XML, and no Green Button either. There is no developer portal, no developer, api, docs or data subdomain, no OpenAPI, and no published third-party data path. What ENMAX does publish openly is grid data. Its Hosting Capacity, Load Capacity and Service Area maps, linked from enmax.com/system-resources, are ArcGIS Online web applications backed by ArcGIS REST feature services that answer anonymous machine-readable queries with no key, no signup and no terms — distribution-feeder DER hosting headroom and remaining load capacity for the Calgary service territory, the data a solar or storage developer actually needs. ENMAX never calls this an API and documents none of it, but it is real, it is open, and it is queryable. Wide open on grid data, completely shut on customer data.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/enmax/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/enmax/refs/heads/main/apis.yml)

## Tags

- Energy
- Canada
- Utilities
- Electricity
- Natural Gas
- Grid
- Smart Metering
- Solar
- DER
- Geospatial
- Alberta
- Electricity Distribution

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### ENMAX Power System Capacity ArcGIS Feature Services

The machine-readable grid data behind ENMAX Power's public Hosting Capacity, Load Capacity and Service Area maps. The three maps published at enmax.com/system-resources are ArcGIS Online Web AppBuilder applications hosted in the GeoARM ArcGIS Online organization, and their operational layers resolve to ArcGIS REST feature services on services1.arcgis.com that answer anonymous queries. `Generation_Capacity_Layers_20250219_PUBLIC` carries estimated remaining DER hosting capacity by distribution feeder segment (fields OBJECTID, FEEDERID, Description, Phase_Designation, Range, Date_Last_Updated), `Feeder_Load_Capacity_Rev9_20251211` carries estimated remaining load capacity as of December 2025, and `ENMAX_Service_Area_for_LAF_Verification` carries the distribution service boundary. Verified anonymously on 2026-07-27: the service directory, each FeatureServer metadata document, and a live `/query` returning attribute rows all responded HTTP 200 with `application/json` and no credential of any kind. This is genuinely open grid data — but it is open by consequence of Esri hosting rather than by design. ENMAX publishes no developer portal, no API reference, no OpenAPI, no rate limits, no terms of use and no versioning policy for these endpoints, and never describes them as an API anywhere on enmax.com. The service names are date-stamped and have already rolled from Rev8 to Rev9, so the paths are not stable contracts. Treat as an undocumented but real public data surface.

- **Human URL:** [https://www.enmax.com/system-resources](https://www.enmax.com/system-resources)
- **Base URL:** `https://services1.arcgis.com/NKgP4VcXUzEyOnmg/arcgis/rest/services`

#### Tags

- Grid
- Hosting Capacity
- Load Capacity
- DER
- Solar
- Geospatial
- Open Data
- Electricity Distribution

#### Properties

- [Documentation](https://www.enmax.com/system-resources)
- [Documentation](https://www.enmax.com/system-resources/hosting-capacity-map)
- [Documentation](https://www.enmax.com/system-resources/load-capacity-map)
- [Documentation](https://www.enmax.com/system-resources/service-area-map)
- [Website](https://services1.arcgis.com/NKgP4VcXUzEyOnmg/arcgis/rest/services?f=json)

## Common Properties

- [Website](https://www.enmax.com/)
- [About](https://www.enmax.com/about-us)
- [Blog](https://www.enmax.com/news)
- [LinkedIn](https://www.linkedin.com/company/enmax)
- [SignUp](https://myaccount.enmax.com/register)
- [Login](https://myaccount.enmax.com/)
- [Support](https://www.enmax.com/customer-support)
- [Status](https://outages.enmax.com/)

## Mandate Posture

| Field | Value |
| --- | --- |
| Mandate regime | `none` |
| Mandate status | `not-applicable` |
| Data standard | no standard reference found |
| Consumer data API | No |
| Market data open | Yes |
| Access gate | `none-published` |
| Home market | Canada |

No consumer energy data mandate applies to ENMAX in any jurisdiction it operates. Alberta has no Green Button regulation; Ontario's O. Reg. 633/21 is province-scoped and does not reach Calgary; Canada has no national energy consumer data right; Maine imposes no Green Button obligation on Versant Power (`https://www.versantpower.com/green-button` renders Versant's own "Page Not Found"). No Green Button Alliance certification was found for any ENMAX group entity.

The split is the story. Consumer usage data is closed harder than usual — ENMAX's own FAQ says Energy Insights "is view-only within your online account and can't be exported at this time," so there is not even a CSV to hand to a third party. Grid data is open — hosting capacity, load capacity and service area layers answer anonymous ArcGIS REST queries with no key and no signup. See [`review.yml`](review.yml) for every URL probed, its HTTP status, and the verbatim evidence.

## Maintainers

- Kin Lane — kin@apievangelist.com
