# Resident Advisor Events Scraper: Ra Scraper API for Python & Node.js (2026)

Scrape Resident Advisor (ra.co) events by city, club or artist: dates, venues, lineups, genres, ticket prices. No login needed. Export JSON, CSV or Excel.

**[▶ Try the Resident Advisor Events Scraper free on Scrapely](https://scrape.ly/store/echofield/resident-advisor-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Ra data with the [Resident Advisor Events Scraper](https://scrape.ly/store/echofield/resident-advisor-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the ra scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Ra scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/resident-advisor-scraper) or from your code with the SDK.
- **Structured ra data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $2.80 per 1,000 event results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Ra changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Ra data can you extract?

Scrape Resident Advisor (ra.co) events by city, club or artist: dates, venues, lineups, genres, ticket prices. No login needed. Export JSON, CSV or Excel.

| Output field |
|---|
| `imageUrl` |
| `title` |
| `date` |
| `startTime` |
| `venueName` |
| `city` |
| `countryCode` |
| `artistNames` |
| `genreNames` |
| `ticketPriceFrom` |
| `ticketCurrency` |
| `interestedCount` |
| `url` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/resident-advisor-scraper').call({"startUrls": [{"url": "https://ra.co/events/uk/london"}], "maxItems": 20, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/resident-advisor-scraper').call(run_input={ "startUrls": [ { "url": "https://ra.co/events/uk/london" } ], "maxItems": 20, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~resident-advisor-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "startUrls": [
    {
      "url": "https://ra.co/events/uk/london"
    }
  ],
  "maxItems": 20,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Resident Advisor Events Scraper page](https://scrape.ly/store/echofield/resident-advisor-scraper).

## Pricing

**$2.80 per 1,000 event results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/resident-advisor-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Ra with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Ra with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a ra scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~resident-advisor-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Ra legal?** This scraper collects publicly available data. Check Ra's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** resident advisor events scraper, ra scraper, ra scraper api, ra scraper python, ra scraper node.js,
scrape ra, ra data extraction, ra crawler, ra api, export ra data to csv, resident-advisor-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/resident-advisor-scraper).
