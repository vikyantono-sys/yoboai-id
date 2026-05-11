# yoboai-id

BigQuery SQL queries and data pipelines for YOBO Indonesia (`qraved-id` GCP project).

## Structure

- `queries/mrr/` — daily MRR, COGS, gross profit calculations
- `queries/merchant_cache/` — per-merchant cache tables (segmentation, win-back, etc.)
- `queries/funnels/` — growth funnel tables for Looker Studio dashboards
- `queries/ops/` — field ops leaderboards, WoW performance tables
- `queries/shared/` — reusable base tables (e.g. `cache_merchant_base_all`)
- `scripts/` — deploy and scheduling helpers
- `docs/` — schema notes, table dependencies, runbooks

## Conventions

- One query per file, named after the destination table.
- Header comment block in every `.sql` file:
```sql
  -- Destination: qraved-id.dataset.table_name
  -- Schedule:    daily 02:00 WIB
  -- Owner:       Viky
  -- Notes:       …
```
- Use `${variable}` placeholders for date ranges or merchant IDs.

## Setup

```bash
git clone https://github.com/vikyantono-sys/yoboai-id.git
cd yoboai-id
```

