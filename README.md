# Real Estate Institute of Australia (reia)

The Real Estate Institute of Australia (REIA), founded in 1924 and based in Canberra, is the national federation of the eight state and territory Real Estate Institutes (REINSW, REIV, REIQ, REIWA, REISA, REIT, REIACT, REINT), which between them represent roughly 85% of Australian real estate businesses and agents. REIA is a policy, research and accreditation body, not an operator of market infrastructure: it administers the REIA National Principles of Conduct that underpin state institute codes and training, awards Associate (AREI) and Fellow accreditations, runs the Australasian Auctioneering Championships (AUSTROS) jointly with REINZ and the National Awards for Excellence (NAFE), makes submissions to the Commonwealth Government, and publishes the quarterly Housing Affordability Report (HAR) and Real Estate Market Facts (REMF) series that Federal Treasury, the Reserve Bank, state treasuries and investment banks subscribe to. It sits well above the transaction rail in the Australian value chain — listings run through REA Group's realestate.com.au and Domain, settlement through PEXA, valuation through PropTrack and CoreLogic, and title through the state land registries — and REIA touches none of those pipes. Its API posture is therefore an honest absence: no developer portal, no API subdomain, no OpenAPI or OData contract, and no RESO reference anywhere on its estate, because RESO is a NAR-mandated United States construct with no Australian counterpart. What REIA sells is data, not access to it — the HAR and REMF reports are AUD 450 subscriptions and each of the 7 HAR and 15 REMF underlying datasets is a separate AUD 280 subscription, delivered as documents through a platformOS/Insites ecommerce storefront with Stripe checkout behind an email-and-password account. Policy submissions, standalone research reports and the strategic plan are freely downloadable PDFs; the quarterly numbers are not, and there is no open data.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/reia/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/reia/refs/heads/main/apis.yml)

## Tags

- Real Estate
- Australia
- Industry Body
- Standards
- Membership
- Property Data
- Housing Affordability
- Research
- Advocacy
- Rentals
- PropTech

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-07-26

## APIs

None. REIA publishes no API. Every developer subdomain probed on both `reia.com.au` and `reia.asn.au` fails to resolve, and every contract path — `/developers`, `/api`, `/docs`, `/openapi.json`, `/swagger.json`, `/api-docs`, `/graphql`, `/wp-json`, `/odata`, `/$metadata` — returns 404. The full sitemap is 19 URLs, none of them a developer page. The only `/api/` reference in the markup is `/api/sessions`, the platformOS session endpoint that the sign-in form POSTs to (GET returns 404, `text/html`); it is CMS plumbing, not a documented API, and it is deliberately not listed.

## RESO Posture

**No RESO reference found — RESO is absent from Australia.** All 19 pages of the site were fetched and grepped for "RESO", "Data Dictionary", "Web API", "OData", "$metadata", "UPI", "REAXML" and "IDX": zero hits. The public RESO certificate directory at [reso.org/certificates](https://www.reso.org/certificates/) (HTTP 200, 416,233 bytes, fetched 2026-07-26) contains no Australian organisation at all — no "Australia", no "REIA", no `.au`. REIA holds **no RESO certification**, and could not: it operates no MLS and holds no listing data.

REIA does list NAR — the body that mandates RESO in the United States — as an alliance on [/our-network](https://www.reia.com.au/our-network), alongside REINZ, FIABCI and ASBEC, plus a relationship with the California Association of REALTORS. That alliance carries no standards obligation into Australia. Australia's machine-readable property rails sit entirely outside REIA: listing syndication with REA Group and Domain, electronic conveyancing with PEXA, valuation with PropTrack and CoreLogic, title with the state land registries.

The standard REIA does administer, the **National Principles of Conduct**, is summarised in prose on [/conduct](https://www.reia.com.au/conduct) but its linked PDF (`reia.com.au/wp-content/uploads/2024/07/Principles-of-Conduct-2012.pdf`) is a dead link to the retired WordPress site and returns **404** — the summary is public, the document is not reachable. The accreditation criteria and application forms **are** freely downloadable PDFs. REIA publishes **no certification directory**; there is nothing analogous to RESO's certificate list.

## Access Gate

**membership-required.** Nothing a developer signs gets them an API, because there is no API. Three gates exist, none of them a developer gate:

1. **Data** — HAR and REMF are sold through the site's platformOS ecommerce module with Stripe checkout: AUD 450 for each flagship report, AUD 280 for each of the 7 HAR and 15 REMF underlying datasets. A buyer creates an account at [/create-account](https://www.reia.com.au/create-account) and accepts terms whose clause 6 forbids reproduction, distribution or resale without written permission and requires attribution to REIA. Subscriptions bill in advance in AUD including GST and auto-renew. The account unlocks documents, not endpoints.
2. **Membership** — REIA's members are the eight state and territory institutes, not individuals. An agent joins their state REI and accepts its Code of Conduct. Affiliate Membership for major networks is by invitation of the REIA Board only.
3. **Accreditation** — AREI and Fellowship both require existing state institute membership, state endorsement, REIA board approval, and a fee (AUD 300 + GST and AUD 850 + GST respectively, payable on approval).

**Auth model:** email and password against the platformOS/Insites account system. No API keys, no OAuth, no SAML/SSO federation, and `/.well-known/openid-configuration` returns 404.

## Open Data

**None.** The quarterly HAR and REMF series — running back to 1982 and subscribed to by Federal Treasury, the Reserve Bank, all state and territory treasuries, investment banks and consultancies — are paid, licensed, document-delivered products. What is freely downloadable without an account (confirmed HTTP 200, `application/pdf`) is advocacy and narrative output: government submissions, standalone research reports (Build to Rent, Property Management Action Plan, CRE EOFY Economic Outlook, CRE Sustainability 2023), the REIA Strategic Plan 2026-28, and AML/CTF fact sheets. All PDFs. None machine-readable, none openly licensed.

## Absences

No webhooks, no SDKs, no GitHub organisation (the GitHub org `reia` is an unrelated Erlang-VM programming language), no Postman collection, no GraphQL, no MCP server, no status page, no changelog, no `security.txt`, and no vulnerability disclosure policy. There is no RSS feed either — `/industry-news/rss` returns HTTP 200 but serves `text/html`, a soft 404; distribution is a monthly email newsletter.

## Common Properties

- [Website](https://www.reia.com.au/)
- [About — Who We Are](https://www.reia.com.au/who-we-are)
- [Network — members, affiliates, partners, alliances](https://www.reia.com.au/our-network)
- [Code of Conduct — REIA National Principles of Conduct](https://www.reia.com.au/conduct)
- [Certification — Associate (AREI) and Fellow accreditation](https://www.reia.com.au/accredit)
- [Research — HAR and REMF](https://www.reia.com.au/research)
- [Pricing — Housing Affordability Report subscriptions](https://www.reia.com.au/research/har)
- [Pricing — Real Estate Market Facts subscriptions](https://www.reia.com.au/research/remf)
- [Reports — standalone research (free PDFs)](https://www.reia.com.au/standalone-research)
- [Policy — submissions to government (free PDFs)](https://www.reia.com.au/submissions)
- [Compliance — AML/CTF obligations from 1 July 2026](https://www.reia.com.au/aml-ctf)
- [News — industry news](https://www.reia.com.au/industry-news)
- [Media contact](https://www.reia.com.au/media-contact)
- [Events — AUSTROS](https://www.reia.com.au/austros)
- [Events — NAFE](https://www.reia.com.au/nafe)
- [Sign in — subscriber portal, not a developer portal](https://www.reia.com.au/sign-in)
- [Terms of Service](https://www.reia.com.au/create-account)
- [Privacy Policy](https://www.reia.com.au/privacy-policy)
- [Disclaimer](https://www.reia.com.au/disclaimer)
- [Contact](https://www.reia.com.au/contact-us)
- [LinkedIn](https://www.linkedin.com/company/real-estate-institute-of-australia-reia)
- [Facebook](https://www.facebook.com/REIAustralia)
- [Instagram](https://www.instagram.com/reiaustralia)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
