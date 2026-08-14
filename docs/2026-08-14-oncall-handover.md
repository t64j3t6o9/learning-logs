# On-call Handover Notes

## Incident: DB connection pool exhaustion (2026-08-14 02:15 KST)

- **Symptom:** Latency spikes, 503s on API gateway
- **Root cause:** Connection leak in batch job (missing `finally` block)
- **Fix:** Added `try-with-resources`; verified with Grafana
- **Follow-up:** Add alert threshold on pool usage > 80%

## Other

- Rotated staging DB credentials
- Updated runbook link in team wiki