# Release readiness and performance evidence

Status cutoff: 12 November 2026. Public evaluation summary, not a production service certificate.

## Current evidence

- Published standalone IMI event/sector analysis exists at POST /v1/analyze, subject to separate plan entitlements.
- An internal separate processing prototype reported successful synthetic adapters and bounded windowed processing tests.
- Sustained full-engine customer throughput is not certified by currently available public evidence. Component tests and observed input traffic are different from completed processing and customer delivery.
- Narrow internal component benchmarks exist but are deliberately not reproduced in this public repository. They do not represent a customer-level service guarantee.
- Benchmark harnesses, parameter settings, internal timing details and source artifacts remain private.
- No sustained end-to-end Full Engine capacity, dedicated tenant isolation, public WSS production availability, commodity readiness or signed end-to-end SLA is established by those component results.

## Measurement boundaries

Component CPU times are not elapsed client times. Decision gate times are not input-to-client signal times. Neither 229 observed producer ticks/sec nor a synthetic stream test establishes that the complete scanner/strategy/delivery path has completed that rate sustainably.

The proposed dedicated WebSocket objective of p99 < 100 ms and the REST objective of p99 < 500 ms are design targets only. Customer-specific guarantees require measured topology, documented clocks and percentiles, an accepted test cohort and a signed service schedule.

## Commercial release checklist

1. Rights: customer-authorized source data and approved derived output/non-display rights.
2. Identity: approved professional customer roles and tenant-specific entitlement.
3. Correctness: versioned input, outputs, missingness, time units and failure behavior.
4. Isolation: independent compute, state, queues, credentials, rate limits and releases.
5. Capacity: completed processing, queue saturation, drops and recovery under sustained load and bursts.
6. Performance: ingest-to-compute-to-gates-to-delivery clocks, including p50, p95, p99 with sample counts.
7. Security: authenticated access, data lifecycle, audit logs, revocation and incident recovery.
8. Contract: output class, customer responsibility, permitted venues, price and mutually agreed SLA.
9. Release proof: installed artifact, deployed hash, rollback, post-deployment public readback.

Until every applicable gate passes, label the service as evaluation-only or proposed. Do not publish benchmarks as a contractually guaranteed end-to-end capability.
