# ENMAX (enmax)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
