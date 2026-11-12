# Public API names and readiness

This document separates published APIs from target institutional contract names. It is not an API availability announcement.

| Path | Purpose | Release state |
| --- | --- | --- |
| `POST /v1/analyze` | Standalone IMI event and sector analysis, using the caller's own permitted headline | Published, with separate entitlement and X-API-Key |
| `WSS /v1/signals/execute` | Full Engine eligible signal stream | Proposed, not publicly available; this name does not indicate brokerage order execution |
| `WSS /v1/stream/greeks` | White-Box approved processed Greeks/indicator stream | Proposed, not publicly available |
| `REST /v1/edge/evaluate` | Candidate-to-Edge Heuristics and ML review | Proposed, not publicly available |
| `REST /v1/edge/historical` | Historic Edge replay from licensed recordings | Proposed, not publicly available |

## Existing IMI REST contract

Published endpoint: `https://api.aionanalytics.in/v1/analyze`.

The client supplies the headline and an eligible `X-API-Key`. The IMI standalone plans do not grant live news-feed ingestion, broker feed delivery or access to the other leased endpoints.

```bash
curl -X POST 'https://api.aionanalytics.in/v1/analyze' \
  -H 'Content-Type: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' \
  -d '{"headline":"Illustrative central bank announcement headline"}'
```

This is a simple input illustration, not an assurance that the headline maps to a specific output or classification. Consult the official published API specification for actual response schemas, entitlements and rate limits.

## Proposed WSS contracts

No public WSS host, path implementation, subscription schema, version, throughput or order contract has been declared production ready. A future client contract must define authentication, message units, timestamp provenance, event ordering, reconnect and resumption, duplicate semantics, backpressure, cancellation and revocation.

No raw tick records, exchange order books or market-data samples will be published as examples. Synthetic processed-output schemas may be supplied only after the public contract is approved.

## Output boundaries

- A signal is an analytical output. It is not a broker order.
- `PASS` does not mean a trade is suitable for every investor or a regulatory approval.
- Unknown or invalid conditions must have explicit refusal or unavailable semantics.
- A developer key for IMI is not entitlement to an institutional stream or a customer broker connection.
- All outputs are limited by the input and derived-data rights established for the customer and use case.
