# NetIntel

Network intelligence API with 44 pay-per-call endpoints for DNS, SSL, WHOIS, email security, web fingerprinting, threat intelligence, and OSINT — powered by [x402](https://www.x402.org/) micropayments.

## Endpoints

| Path | Method | Price | Description |
|------|--------|-------|-------------|
| `/dns/lookup` | GET | $0.030 | Resolves all DNS record types for a domain, parses SPF/DKIM/DMARC from TXT records, and compares A… |
| `/ssl/analyze` | GET | $0.030 | Performs a TLS handshake to inspect the certificate chain, probes supported TLS versions (1.0–1.3)… |
| `/redirect/trace` | GET | $0.010 | Follows a URL through its full redirect chain (up to 20 hops), recording status codes, timing… |
| `/security-headers/analyze` | GET | $0.010 | Fetches a URL and evaluates 10 security-critical response headers (CSP, HSTS… |
| `/email-auth` | POST | $0.030 | Validates SPF, DKIM, and DMARC records for a domain, probes multiple DKIM selectors concurrently… |
| `/cloud-fingerprint/analyze` | GET | $0.010 | Fingerprints a domain's cloud infrastructure by probing DNS records, HTTP headers, and PTR lookups… |
| `/schema-parse/extract` | POST | $0.100 | Accepts unstructured text and a JSON Schema, then uses an LLM to extract structured data matching… |
| `/asn-lookup/analyze` | GET | $0.030 | Resolves an IP address or domain to its Autonomous System Number (ASN), network owner, country, and… |
| `/whois-rdap/lookup` | GET | $0.010 | Look up domain registration metadata via RDAP — returns registrar, creation/expiry dates… |
| `/cert-transparency/lookup` | GET | $0.010 | Query the crt.sh certificate transparency log database to enumerate all SSL certificates ever… |
| `/subnet/calc` | GET | $0.005 | Calculates IPv4/IPv6 subnet details from CIDR notation including network/broadcast addresses… |
| `/dns-propagation/check` | GET | $0.030 | Query a domain's DNS record across 10 geographically distributed public resolvers simultaneously —… |
| `/dnssec/validate` | GET | $0.030 | Validate a domain's DNSSEC configuration by checking for DS records at the parent zone, DNSKEY… |
| `/ip-blacklist/check` | GET | $0.050 | Check an IP address against 15 major DNS blacklists (Spamhaus, Barracuda, SORBS, etc.)… |
| `/ip-reputation/analyze` | GET | $0.050 | Check an IP address against AbuseIPDB and AlienVault OTX threat feeds. Returns a composite risk… |
| `/cron-parser/explain` | GET | $0.030 | Parse any cron expression into a human-readable explanation, validate its syntax, compute the next… |
| `/currency-exchange/convert` | GET | $0.010 | Convert any amount between 33 currencies using live European Central Bank exchange rates — returns… |
| `/tech-fingerprint/analyze` | GET | $0.050 | Fetch a URL and detect the full technology stack from HTTP response headers, HTML meta tags… |
| `/breach-check/password` | GET | $0.010 | Check if a password has appeared in known data breaches using the HaveIBeenPwned Pwned Passwords… |
| `/domain-availability/check` | GET | $0.050 | Check if a domain name is available for registration by querying RDAP and DNS — returns… |
| `/email-intel/analyze` | GET | $0.050 | Validate an email address for deliverability, detect disposable/temporary domains, identify… |
| `/og-scraper/extract` | GET | $0.010 | Fetch any public URL and extract structured metadata — Open Graph tags, Twitter Card tags… |
| `/page-extract/read` | GET | $0.050 | Fetch any article or web page and extract clean readable text stripped of navigation, ads, and… |
| `/phone-intel/analyze` | GET | $0.050 | Parse and validate any phone number in any format, identify its country, line type… |
| `/robots-txt/analyze` | GET | $0.010 | Fetch and parse a domain's robots.txt file — returns all crawl rules by user-agent, sitemap URLs… |
| `/rss-parser/fetch` | GET | $0.010 | Fetch and parse any RSS 2.0 or Atom feed URL and return structured articles with title, link… |
| `/username-check/lookup` | GET | $0.030 | Check username availability across 20+ social platforms and developer sites simultaneously —… |
| `/wayback/lookup` | GET | $0.010 | Query the Internet Archive Wayback Machine to check if a URL has ever been archived, get the… |
| `/domain-age/check` | GET | $0.030 | Determine a domain's age from registration data and archival history — returns creation date, age… |
| `/github-intel/analyze` | GET | $0.030 | Fetch public metadata for any GitHub repository — stars, forks, open issues, language breakdown… |
| `/holidays/check` | GET | $0.005 | Look up public holidays for any country and year, check whether a specific date is a holiday, and… |
| `/ip-geo/locate` | GET | $0.030 | Geolocate any IPv4 or IPv6 address to city, region, country, latitude/longitude, timezone, and… |
| `/jwt-inspector/decode` | GET | $0.005 | Decode and inspect any JWT token — extracts header algorithm, payload claims, expiry status… |
| `/lang-detect/analyze` | POST | $0.005 | Detect the language of any text input using character frequency analysis and n-gram pattern… |
| `/npm-intel/analyze` | GET | $0.010 | Fetch metadata for any npm package — download counts, latest version, all versions list… |
| `/sitemap-parser/fetch` | GET | $0.010 | Fetch and parse any XML sitemap or sitemap index file — returns all URLs with their priority… |
| `/url-safety/check` | GET | $0.050 | Check a URL against URLhaus malware database and heuristic phishing pattern analysis — returns… |
| `/bulk-domain/check` | POST | $0.100 | Check availability of many domain names across multiple TLDs in a single call — submit up to 50… |
| `/domain-appraise/estimate` | GET | $0.030 | Estimate the market value tier of a domain name using transparent heuristics — length, TLD premium… |
| `/domain-report/analyze` | GET | $0.100 | One call returns a complete intelligence profile for a domain — WHOIS registration, DNS records… |
| `/ip-risk/score` | GET | $0.100 | One call returns a complete risk profile for an IP address — geolocation, ASN/network owner… |
| `/name-gen/suggest` | GET | $0.050 | Generate brandable startup/product names from a keyword using prefixes, suffixes, blends, and… |
| `/tld-price/compare` | GET | $0.010 | Compare registration, renewal, and transfer prices for a TLD across major registrars, or for a… |
| `/typosquat/scan` | GET | $0.050 | Generate common typo and look-alike variations of a domain and check which are already registered —… |

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
| Price range | $0.005 – $0.100 per call |

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