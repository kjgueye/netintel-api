# NetIntel

Network intelligence API with 126 pay-per-call endpoints for DNS, SSL, WHOIS, email security, web fingerprinting, threat intelligence, and OSINT — powered by [x402](https://www.x402.org/) micropayments.

**Discover & call NetIntel on Coinbase's [Agentic.Market ↗](https://agentic.market/services/netintel-dev)** — all endpoints, live pricing, and a one-paste agent SKILL.md. Also: [llms.txt](https://netintel.dev/llms.txt) · [x402 manifest](https://netintel.dev/.well-known/x402) · MCP: `npx -y netintel-mcp`

## Endpoints

| Path | Method | Price | Description |
|------|--------|-------|-------------|
| `/dns/lookup` | GET | $0.002 | DNS lookup / nslookup / dig API — resolve the common DNS record types (A, AAAA, MX, TXT, NS, CNAME… |
| `/ssl/analyze` | GET | $0.007 | Performs a TLS handshake to inspect the certificate chain, probes supported TLS versions (1.0–1.3)… |
| `/ssl/cert` | GET | $0.003 | Fast SSL/TLS certificate facts for any domain — issuer, subject, SANs, valid from/to, days until… |
| `/ssl/cert` | POST | $0.003 | Fast SSL/TLS certificate facts for any domain — issuer, subject, SANs, valid from/to, days until… |
| `/redirect/trace` | GET | $0.010 | Follows a URL through its full redirect chain (up to 20 hops), recording status codes, timing… |
| `/security-headers/analyze` | GET | $0.010 | Fetches a URL and evaluates 10 security-critical response headers (CSP, HSTS… |
| `/email-auth` | POST | $0.002 | Email deliverability & domain security check — validates SPF, DKIM (multi-selector), and DMARC… |
| `/cloud-fingerprint/analyze` | GET | $0.010 | Fingerprints a domain's cloud infrastructure by probing DNS records, HTTP headers, and PTR lookups… |
| `/schema-parse/extract` | POST | $0.010 | Extract structured data from any unstructured text into your own JSON Schema — structured-data /… |
| `/messages` | POST | $0.06 | OpenAI-compatible chat completions over x402, answered by Claude Sonnet 4.6 — send a messages array… |
| `/openai/gpt-4o` | POST | $0.10 | Call OpenAI's gpt-4o via a single pay-per-call x402 endpoint — no OpenAI account or API key needed… |
| `/openai/gpt-4-1` | POST | $0.09 | Call OpenAI's gpt-4.1 via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-4-1-mini` | POST | $0.005 | Call OpenAI's gpt-4.1-mini via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/v1/embeddings` | POST | $0.005 | OpenAI-compatible text embeddings API — standard /v1/embeddings request shape: input as a string or… |
| `/embeddings` | POST | $0.001 | Multilingual text embeddings (384-dim) served in-house, no OpenAI dependency, no API key… |
| `/semantic/rank` | POST | $0.02 | Semantic similarity ranking — send a query plus up to 100 candidate texts, get the candidates back… |
| `/v1/chat/completions` | POST | $0.005 | OpenAI-compatible chat completions gateway — standard /v1/chat/completions path and request shape… |
| `/openai/gpt-4o-mini` | POST | $0.005 | Call OpenAI's gpt-4o-mini via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-4-1-nano` | POST | $0.005 | Call OpenAI's gpt-4.1-nano via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-5` | POST | $0.65 | Call OpenAI's gpt-5.5 via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-4` | POST | $0.25 | Call OpenAI's gpt-5.4 via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-4-mini` | POST | $0.04 | Call OpenAI's gpt-5.4-mini via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-4-nano` | POST | $0.005 | Call OpenAI's gpt-5.4-nano via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-1` | POST | $0.15 | Call OpenAI's gpt-5.1 via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-nano` | POST | $0.005 | Call OpenAI's gpt-5-nano via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-2` | POST | $0.20 | Call OpenAI's gpt-5.2 via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-6-sol` | POST | $0.65 | Call OpenAI's gpt-5.6-sol via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-6-terra` | POST | $0.25 | Call OpenAI's gpt-5.6-terra via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/openai/gpt-5-6-luna` | POST | $0.06 | Call OpenAI's gpt-5.6-luna via a single pay-per-call x402 endpoint — no OpenAI account or API key… |
| `/ai-image/generate` | POST | $0.25 | Generate agent-ready image assets (icons, logos, social graphics, thumbnails, banners) with… |
| `/classify` | POST | $0.005 | Text classification API — zero-shot text classifier / categorization: caller supplies 2–20 labels… |
| `/content-moderate` | POST | $0.005 | Moderate text content using Claude Haiku — flags categories like harassment, hate, sexual content… |
| `/entity-extract` | POST | $0.050 | Extract named entities from text using Claude Haiku — people, organizations, locations, dates… |
| `/extract/address` | POST | $0.01 | Parse and normalize a freeform address string using Claude Haiku — splits it into street, city… |
| `/extract/contact` | POST | $0.01 | Extract structured contact details from text, an email signature, or webpage text using Claude… |
| `/extract/invoice` | POST | $0.02 | Extract structured data from invoice or receipt text — or directly from an invoice URL (PDF, HTML… |
| `/extract/resume` | POST | $0.02 | Extract structured data from resume/CV text using Claude Haiku — returns name, contact info… |
| `/extract/table` | POST | $0.02 | Extract tabular data from messy text or HTML using Claude Haiku — detects columns and rows in… |
| `/markdown/clean` | POST | $0.03 | Convert messy HTML or text into clean, well-structured Markdown using Claude Haiku — strips… |
| `/normalize/json` | POST | $0.05 | Conform messy or inconsistent JSON to a target schema using Claude Haiku — renames keys, coerces… |
| `/text-to-json` | POST | $0.05 | Turn unstructured text into structured JSON matching a caller-supplied schema using Claude Haiku —… |
| `/sentiment/analyze` | POST | $0.002 | Sentiment analysis API — analyze sentiment of text and get a text sentiment score in one call:… |
| `/text-summarize` | POST | $0.005 | Text summarizer / summarization API — condense text, Markdown, or a URL into a TL;DR plus key… |
| `/text/chunk` | POST | $0.001 | Split text into overlapping chunks for RAG ingestion — by characters or words, with configurable… |
| `/text/stats` | GET | $0.001 | Instant text statistics — characters (with/without spaces), words, unique words, sentences… |
| `/text/stats` | POST | $0.001 | Instant text statistics — characters (with/without spaces), words, unique words, sentences… |
| `/translate/long` | POST | $0.02 | Translate up to 2000 words between languages using Claude Haiku — auto-detects source, supports 30+… |
| `/translate/structured` | POST | $0.02 | Translate structured content — JSON, HTML, Markdown, templates, UI strings — without breaking… |
| `/translate/batch` | POST | $0.05 | Translate many independent strings in one request — each with a caller ID preserved in the response… |
| `/translate/short` | POST | $0.01 | Translate text between languages — text translation API for short content: translate a sentence… |
| `/asn-lookup/analyze` | GET | $0.030 | Resolves an IP address or domain to its Autonomous System Number (ASN), network owner, country, and… |
| `/whois-rdap/lookup` | GET | $0.003 | WHOIS domain lookup via RDAP — registrar, creation/expiry/updated dates, nameservers, and status… |
| `/cert-transparency/lookup` | GET | $0.010 | Query the crt.sh certificate transparency log database to enumerate all SSL certificates ever… |
| `/subnet/calc` | GET | $0.005 | Calculates IPv4/IPv6 subnet details from CIDR notation — network/broadcast, netmask, wildcard… |
| `/dns-propagation/check` | GET | $0.030 | Query a domain's DNS record across 10 geographically distributed public resolvers simultaneously —… |
| `/dnssec/validate` | GET | $0.030 | Validate a domain's DNSSEC configuration over DNS-over-HTTPS: DS records at the parent zone, DNSKEY… |
| `/ip-blacklist/check` | GET | $0.050 | Check an IP address against 15 major DNS blacklists (Spamhaus, Barracuda, SORBS, etc.)… |
| `/ip-reputation/analyze` | GET | $0.050 | Check an IP address against AbuseIPDB and AlienVault OTX threat feeds. Returns a composite risk… |
| `/cron-parser/explain` | GET | $0.030 | Parse any cron expression into a human-readable explanation, validate its syntax, compute the next… |
| `/currency-exchange/convert` | GET | $0.010 | Convert any amount between 32 fiat currencies (live European Central Bank rates) and major… |
| `/crypto/market` | GET | $0.005 | Structured live crypto market data for ~50 top assets in one JSON call: spot price and 24h… |
| `/gas/price` | GET | $0.002 | Live gas prices across Base, Ethereum, Arbitrum, Optimism, and Polygon with USD cost estimates for… |
| `/crypto/price` | GET | $0.005 | Spot prices for up to 25 crypto assets in one call — USD, EUR, or GBP — from Coinbase with Kraken… |
| `/crypto/ohlc` | GET | $0.02 | Historical OHLC candles for any major crypto asset — hourly or daily, up to 300 candles, with… |
| `/currency-exchange/batch` | GET | $0.02 | Convert one base currency to up to 30 targets in a single call — fiat (~200 currencies incl. SAR… |
| `/currency-exchange/history` | GET | $0.02 | Daily historical exchange-rate series for any currency pair — fiat via ECB reference data, crypto… |
| `/token/info` | GET | $0.02 | Full profile for any ERC-20 token by contract address — name, symbol, decimals, supply from the… |
| `/wallet/balance` | GET | $0.005 | Native + USDC + custom-token balances for any wallet on Base, Ethereum, or Solana — with USD… |
| `/wallet/intel` | GET | $0.05 | Counterparty due-diligence for any Base or Ethereum wallet — age, funding origin, USDC flow… |
| `/iban/validate` | GET | $0.005 | Validate any IBAN offline — mod-97 check digits, per-country structure, bank/branch extraction, and… |
| `/iban/validate` | POST | $0.005 | Validate any IBAN offline — mod-97 check digits, per-country structure, bank/branch extraction, and… |
| `/weather/current` | GET | $0.002 | Live weather + 3-day forecast for any city or lat/lon worldwide — temperature, feels-like… |
| `/weather/current` | POST | $0.002 | Live weather + 3-day forecast for any city or lat/lon worldwide — temperature, feels-like… |
| `/weather/forecast` | GET | $0.003 | Multi-day weather forecast for any city or lat/lon worldwide — up to 16 days of daily highs/lows… |
| `/weather/forecast` | POST | $0.003 | Multi-day weather forecast for any city or lat/lon worldwide — up to 16 days of daily highs/lows… |
| `/prediction/markets` | GET | $0.005 | Live prediction-market odds from Polymarket — list the top active markets by volume, or search by… |
| `/prediction/markets` | POST | $0.005 | Live prediction-market odds from Polymarket — list the top active markets by volume, or search by… |
| `/prediction/market` | GET | $0.003 | Full detail for ONE Polymarket prediction market by id or slug — question, description, every… |
| `/prediction/market` | POST | $0.003 | Full detail for ONE Polymarket prediction market by id or slug — question, description, every… |
| `/market/snapshot` | GET | $0.05 | One-call market briefing for agents — BTC/ETH/SOL spot + 24h moves, major fiat crosses (USD/EUR… |
| `/convert` | GET | $0.01 | Convert any physical measurement — length, mass, volume, temperature, area, speed, pressure… |
| `/money/parse` | POST | $0.01 | Normalize any messy money string into a typed decimal amount plus ISO 4217 currency — handles… |
| `/json/repair` | POST | $0.02 | Repair malformed JSON into valid JSON — fixes code fences, trailing commas, single quotes, unquoted… |
| `/schema/validate` | POST | $0.02 | Validate data against a supplied schema — checks required fields, nested objects, arrays, enums… |
| `/schema/map` | POST | $0.04 | Transform a source object into a target schema — matches fields by alias and structure… |
| `/calendar/ics` | POST | $0.005 | Turn event fields into a valid RFC 5545 .ics calendar file — handles timed and all-day events… |
| `/event-classify` | POST | $0.02 | Cheap, fast "is this a dateable event?" filter for social and web text — one tiny Haiku call… |
| `/event-extract` | POST | $0.050 | Event extraction / event parsing — turn any caption, announcement, listing, or page text into a… |
| `/tech-fingerprint/analyze` | GET | $0.050 | Fetch a URL and detect the full technology stack from HTTP response headers, HTML meta tags… |
| `/breach-check/password` | GET | $0.010 | Check if a password has appeared in known data breaches using the HaveIBeenPwned Pwned Passwords… |
| `/domain-availability/check` | GET | $0.010 | Check if a domain name is available for registration by querying RDAP and DNS — pass a bare name… |
| `/email-intel/analyze` | GET | $0.005 | Email verification & deliverability check (email validator / verifier) — validate an address… |
| `/og-scraper/extract` | GET | $0.010 | Fetch any public URL and extract structured metadata — Open Graph tags, Twitter Card tags… |
| `/page-extract/read` | GET | $0.050 | Fetch any article or web page and extract clean readable text stripped of navigation, ads, and… |
| `/web/extract` | GET | $0.003 | Extract article / main content from any URL or PDF to clean, LLM-ready Markdown (web scraper /… |
| `/phone-intel/analyze` | GET | $0.050 | Parse and validate any phone number in any format, identify its country and line type… |
| `/robots-txt/analyze` | GET | $0.010 | Fetch and parse a domain's robots.txt file — returns all crawl rules by user-agent, sitemap URLs… |
| `/rss-parser/fetch` | GET | $0.010 | Fetch and parse any RSS 2.0 or Atom feed URL and return structured articles with title, link… |
| `/username-check/lookup` | GET | $0.030 | Check username availability across 20+ social platforms and developer sites simultaneously —… |
| `/wayback/lookup` | GET | $0.010 | Query the Internet Archive Wayback Machine to check if a URL has ever been archived, get the… |
| `/domain-age/check` | GET | $0.030 | Determine a domain's age from registration data and archival history — tries RDAP, then port-43… |
| `/web/fetch` | GET | $0.003 | Fetch any URL and get the raw body back — JSON parsed, everything else as text — from safe… |
| `/web/fetch` | POST | $0.003 | Fetch any URL and get the raw body back — JSON parsed, everything else as text — from safe… |
| `/github-intel/analyze` | GET | $0.030 | Fetch public metadata for any GitHub repository — stars, forks, open issues, language breakdown… |
| `/github-intel/analyze` | POST | $0.030 | Fetch public metadata for any GitHub repository — stars, forks, open issues, language breakdown… |
| `/holidays/check` | GET | $0.005 | Look up public holidays for any country and year, check whether a specific date is a holiday, and… |
| `/ip-geo/locate` | GET | $0.002 | IP geolocation lookup (geoip / IP location API) — geolocate any IPv4 or IPv6 address to city… |
| `/jwt-inspector/decode` | GET | $0.005 | Decode and inspect any JWT token — extracts header algorithm, payload claims, expiry status… |
| `/lang-detect/analyze` | POST | $0.005 | Detect the language of any text input using stopword-set matching and Unicode script analysis —… |
| `/npm-intel/analyze` | GET | $0.010 | Fetch metadata for any npm package — download counts, latest version, version count… |
| `/sitemap-parser/fetch` | GET | $0.010 | Fetch and parse any XML sitemap or sitemap index file — returns URLs with their priority, change… |
| `/url-safety/check` | GET | $0.010 | Check a URL against URLhaus malware database and heuristic phishing pattern analysis — returns… |
| `/bulk-domain/check` | POST | $0.100 | Check availability of many domain names across multiple TLDs in a single call — submit up to 50… |
| `/domain-appraise/estimate` | GET | $0.030 | Estimate the market value tier of a domain name using transparent heuristics — length, TLD premium… |
| `/domain-report/analyze` | GET | $0.100 | One call returns a complete intelligence profile for a domain — WHOIS registration, DNS records… |
| `/ip-risk/score` | GET | $0.100 | One call returns a complete risk profile for an IP address — geolocation, ASN/network owner… |
| `/name-gen/suggest` | GET | $0.050 | Generate brandable startup/product names from a keyword using prefixes, suffixes, blends, and… |
| `/tld-price/compare` | GET | $0.010 | Reference registration/renewal/transfer pricing from a curated table of ~21 common TLDs — Mode A:… |
| `/typosquat/scan` | GET | $0.050 | Generate common typo and look-alike variations of a domain and check which are already registered —… |
| `/domain-due-diligence` | GET | $0.20 | One call combines domain availability, heuristic value appraisal, and TLD pricing into a single… |
| `/domain-report/full` | GET | $0.25 | One premium call returns a complete six-part domain profile — DNS records, SSL certificate, WHOIS… |
| `/domain/vendor-risk` | POST | $0.10 | Composite 0-100 trust/risk score for a domain in one call — blends domain age, SSL/TLS, DNS health… |
| `/domain/vet` | POST | $0.20 | Vet and pick a domain in one call — give candidate names, get back a ranked verdict on which to use… |
| `/email-report/full` | GET | $0.15 | One call combines domain email authentication (SPF/DKIM/DMARC), email-address intelligence… |
| `/ip-report/full` | GET | $0.20 | One premium call returns a complete five-part IP profile — geolocation, ASN/network ownership… |
| `/url-safety/full` | GET | $0.15 | One call vets a URL end to end — traces its full redirect chain, checks it against the URLhaus… |

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