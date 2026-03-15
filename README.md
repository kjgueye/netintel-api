# NetIntel

Network intelligence API with 25 pay-per-call endpoints for DNS, SSL, WHOIS, email security, web fingerprinting, and OSINT — powered by [x402](https://www.x402.org/) micropayments.

## Endpoints

| Path | Method | Price | Description |
|------|--------|-------|-------------|
| `/dns/lookup` | GET | $0.001 | Resolve all DNS record types, parse SPF/DKIM/DMARC, check propagation |
| `/ssl/analyze` | GET | $0.001 | TLS handshake, certificate chain, supported protocols, security grade |
| `/subnet/calc` | GET | $0.001 | CIDR analysis, host range, supernet/subnets, overlap detection |
| `/redirect/trace` | GET | $0.001 | Follow redirect chain with per-hop timing, headers, TLS status |
| `/security-headers/analyze` | GET | $0.001 | Audit 10 security headers, detect anti-patterns, grade A–F |
| `/email-auth` | POST | $0.004 | Validate SPF, DKIM, DMARC with multi-selector probing |
| `/cloud-fingerprint/analyze` | GET | $0.002 | Detect CDN, WAF, hosting, DNS, and email providers |
| `/schema-parse/extract` | POST | $0.005 | LLM-powered structured data extraction from unstructured text |
| `/asn-lookup/analyze` | GET | $0.001 | IP/domain to ASN, org, country, hosting/cloud classification |
| `/whois-rdap/lookup` | GET | $0.001 | Domain registration via RDAP — registrar, dates, nameservers |
| `/cert-transparency/lookup` | GET | $0.002 | Search crt.sh for certificates, subdomains, issuers |
| `/dns-propagation/check` | GET | $0.003 | Query 10 global resolvers, compare results, propagation % |
| `/dnssec/validate` | GET | $0.002 | Check DS, DNSKEY, RRSIG, NSEC/NSEC3 chain of trust |
| `/ip-blacklist/check` | GET | $0.003 | Check IP against 15 DNS blacklists simultaneously |
| `/tech-fingerprint/analyze` | GET | $0.002 | Detect CMS, framework, CDN, server, analytics from HTTP |
| `/breach-check/password` | GET | $0.001 | k-anonymity check against HaveIBeenPwned (password never sent) |
| `/domain-availability/check` | GET | $0.002 | Check registration status across 10 TLDs via RDAP+DNS |
| `/email-intel/analyze` | GET | $0.002 | Validate deliverability, detect disposable/role-based addresses |
| `/og-scraper/extract` | GET | $0.001 | Extract Open Graph, Twitter Card, JSON-LD, favicon metadata |
| `/page-extract/read` | GET | $0.002 | Extract clean readable text, word count, reading time |
| `/phone-intel/analyze` | GET | $0.001 | Parse, validate, classify phone numbers (type, country, format) |
| `/robots-txt/analyze` | GET | $0.001 | Parse robots.txt rules, sitemaps, check path permissions |
| `/rss-parser/fetch` | GET | $0.001 | Parse RSS 2.0 and Atom feeds into structured items |
| `/username-check/lookup` | GET | $0.003 | Check username across 20+ platforms simultaneously |
| `/wayback/lookup` | GET | $0.001 | Query Wayback Machine for snapshots and archival history |

## Usage

No API key or signup required. Every request is authenticated by payment.

```bash
# Without payment — returns 402 with payment requirements
curl https://netintel-production-440c.up.railway.app/dns/lookup?domain=example.com

# With x402 payment (using @x402/fetch or any x402 client)
import { wrapFetchWithPayment } from "@x402/fetch";

const payFetch = wrapFetchWithPayment(fetch, client);
const res = await payFetch(
  "https://netintel-production-440c.up.railway.app/dns/lookup?domain=example.com"
);
const data = await res.json();
```

## Payment

All endpoints require USDC micropayment on **Base mainnet** via the [x402 protocol](https://www.x402.org/).

| Field | Value |
|-------|-------|
| Network | Base mainnet (`eip155:8453`) |
| Currency | USDC |
| Scheme | `exact` |
| Facilitator | `https://api.cdp.coinbase.com/platform/v2/x402` |
| Payee wallet | `0xdaDc335482AD545296Fd7b28518A251fFCbEb9Df` |
| Price range | $0.001 – $0.005 per call |

Send a valid `X-Payment` header with each request. Without it, endpoints return HTTP 402 with payment requirements in the `PAYMENT-REQUIRED` response header.

## Free endpoints

| Path | Description |
|------|-------------|
| `GET /health` | Server health check |
| `GET /openapi.json` | OpenAPI 3.1 spec |
| `GET /.well-known/x402` | [x402 discovery manifest](https://netintel-production-440c.up.railway.app/.well-known/x402) |

## Links

- **API Manifest:** https://netintel-production-440c.up.railway.app/.well-known/x402
- **OpenAPI Spec:** https://netintel-production-440c.up.railway.app/openapi.json
- **Bazaar Listing:** https://api.cdp.coinbase.com/platform/v2/x402/discovery/resources
