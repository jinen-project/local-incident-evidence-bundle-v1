# Local Incident Evidence Bundle v1

Turn a small stream of incident events into a local timeline, evidence map, and review bundle you can inspect.

`POST /incident-events` accepts a bounded event. Formed events are handed to Local Receipted Handoff, then enter an append-only local journal. Run `npm run demo` for three formed events, a matched non-formed event, a replay, deterministic timeline, review, and Evidence Packet artifacts.

## Install

```sh
git clone https://github.com/jinen-project/local-incident-evidence-bundle-v1.git
cd local-incident-evidence-bundle-v1
npm install
npm start
```

Use `POST /incident-events` with `incident_id`, `event_id`, `occurred_at`, `source`, `kind`, and `summary`. `FORMED` means the configured local ingress accepted and wrote the bounded event; `NOT_FORMED` means no journal event is created; `DUPLICATE` means no second journal event is created.

Output bundles contain `events.ndjson`, `timeline.md`, `incident-review.md`, `evidence-packet.json`, `evidence-packet.md`, and `bundle.json` under `.lieb/incidents/<incident_id>/`.

## Boundaries

This is not incident management, monitoring, paging, root-cause determination, or a claim that events are true. `TIMELINE != CAUSATION`; `SOURCE_TIMESTAMP != INDEPENDENTLY_VERIFIED_TIME`; `SUPPORTED_CLAIM != GLOBAL_TRUTH`; `NO_EVIDENCE != FALSE`; `ERROR_RATE_RECOVERED != INCIDENT_RESOLVED`; and a local bundle is not complete incident history. Free: no account, billing, paywall, or trial limit.
