# Truth Bear — verifiable official-source data for AI agents (MCP)

Neutral, third-party access to **official public records** — US federal agencies, named registries and standards bodies — where **every paid record ships an offline-recomputable `record_hash` and an Ed25519-signed citation**. Pay per call in USDC via x402. No account, no API key.

Truth Bear **restates official records faithfully; it does not adjudicate, advise, or endorse**. The authoritative source is the official publisher named in every citation — verify and dispute there.

---

## Add it (remote MCP server)

```json
{
  "mcpServers": {
    "truthbear": { "url": "https://api.truthbear.co/mcp" }
  }
}
```

JSON-RPC 2.0 over HTTP POST (`initialize` / `tools/list` / `tools/call`). No key needed to list or verify; paid tools return a real x402 payment challenge you settle from your own wallet.

## Tools

| Tool | Cost | What it does |
|---|---|---|
| `find_signal` | FREE | Coverage + freshness: which signals exist, queryable before you pay |
| `verify_citation` | FREE | Check a `record_hash`, get the official reverse-lookup |
| `purchase_options` | FREE | How to pay for a listed endpoint |
| `verify_triangular` | FREE | Cross-verify one interwoven official line |
| `get_official_record` | x402 | Returns a real payment challenge; pay, then receive the signed official record |

## What you pay for

Not the raw public number (free at its source) — the **aggregation + official-source provenance + offline cryptographic verifiability**, pre-joined into one schema.

## Verify offline, against the primary source

Every paid record carries a `record_hash` (canonical sha256, independently recomputable) and an Ed25519 citation. SEC-filing settlement evidence also ships a `durable_anchor` (an immutable SEC accession + permanent document URL) that re-verifies at any time, not only at read time.

## Coverage (90 industries)

Macro (FRED / US Treasury / BLS), energy (EIA), weather & disaster (NOAA / USGS / NWS / SPC / FEMA), health (openFDA / CDC), sanctions (OFAC / EU), trade (USITC), **SEC EDGAR filings**, and more.

## Try it

```bash
# free: what exists
curl https://api.truthbear.co/manifest

# free: MCP tool list
curl "https://api.truthbear.co/manifest?platform=mcp"

# settlement evidence feed (x402, $0.01): did an issuer file a form before a cutoff?
curl "https://api.truthbear.co/resolve/proposer?entity=AAPL&form=10-K&cutoff=2025-11-15"
```

## Terms

Third-party relay of official records plus cross-source analysis. We warrant **faithful relay** (the hash recomputes against the cited official source), **not** the correctness of the source itself. Reference only — not advice, not adjudication, not a market resolution; the independent judgement and decision are the user's own. Full provider notice: https://api.truthbear.co/terms

## Links

- MCP endpoint: https://api.truthbear.co/mcp
- Manifest: https://api.truthbear.co/manifest
- Capability / discovery: https://api.truthbear.co/.well-known/x402 · https://api.truthbear.co/llms.txt
- Terms: https://api.truthbear.co/terms

## License

MIT (this listing/readme). The API itself is a hosted service governed by the Terms above.
