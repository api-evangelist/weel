# Weel (weel)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Weel (formerly DiviPay, operated by Weel Pty Ltd) is a Melbourne-based all-in-one spend management platform for finance teams in Australia and New Zealand, serving 4,000+ finance teams and 60,000+ card holders. Weel issues virtual and physical Visa debit cards with real-time limits and controls, and layers accounts payable automation, expense management, reimbursements, subscription management, budgets, and approval policies on top — syncing approved spend into Xero, QuickBooks, MYOB, and NetSuite. Its public developer portal documents a single RESTful Weel Open API that both reads and writes budgets, users, transactions, custom fields, accounting codes, and top-ups, authenticated with a bearer API key.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/weel/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/weel/refs/heads/main/apis.yml)

## Tags

- Payments
- Australia
- Spend Management
- Expense Management
- Corporate Cards
- Accounts Payable
- Card Issuing
- Reimbursements
- Budgets
- Fintech

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Weel Open API

The Weel Open API is a single RESTful interface that programmatically reads and writes a business's spend data in Weel — budgets, budget members, budget owners, budget top-ups, users, roles, transactions, statements, invites, categories, tax rates, accounting codes, and custom fields — to automate expense workflows and build custom integrations. OpenAPI 3.1.0, 30 documented operations across 15 resource tags, authenticated with a bearer API key (generated in-app under Settings > API). API access is available on the Enterprise plan.

- **Human URL:** [https://developer.letsweel.com/openapi](https://developer.letsweel.com/openapi)
- **Base URL:** `https://public.letsweel.com`

#### Tags

- Spend Management
- Expense Management
- Budgets
- Transactions
- Card Issuing

#### Properties

- [OpenAPI](openapi/weel-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developer.letsweel.com/)
- [API Reference](https://developer.letsweel.com/openapi)
- [Authentication](https://developer.letsweel.com/getting-started/authentication)
- [Getting Started](https://developer.letsweel.com/getting-started/authentication)

## Common Properties

- [Website](https://letsweel.com/)
- [Developer Portal](https://developer.letsweel.com/)
- [Documentation](https://developer.letsweel.com/)
- [API Reference](https://developer.letsweel.com/openapi)
- [Getting Started](https://developer.letsweel.com/getting-started/authentication)
- [Pricing](https://letsweel.com/pricing)
- [Change Log](https://letsweel.com/product-updates)
- [Trust Center](https://trust.letsweel.com/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
