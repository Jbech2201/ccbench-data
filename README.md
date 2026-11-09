# ccbench-data

Raw measurement data from **ccbench** congestion-control benchmarking experiments over a Starlink link.

## Contents

| Path | Description |
| --- | --- |
| `laporan-verifikasi-putaran1.pdf` | Verification report, round 1 (Indonesian) |
| `mentah/` | Raw experiment data and provenance |
| `uplink5x5-starlink-20261109T203631Z/` | 5×5 uplink test set (rounds 1–2) |

### Top-level files

- `uplink5x5-starlink-20261109T203631Z.console.log` — console log for the 5×5 uplink run.

### `mentah/` (raw data)

Each experiment directory follows the pattern:

```
<experiment>-<timestamp>Z/
  data/
    uplink/    (per-algorithm logs, e.g. indigo, pcc, taova, vivace, _refNN_cubic)
    downlink/  (same layout)
  provenance/
    patches/
  *.console.log / *.collect.log
```

Experiment runs present:

| Directory | Notes |
| --- | --- |
| `starlink-params-20261107T112310Z`, `starlink-params-20261107T112621Z` | Starlink parameter measurement |
| `gladi-dress-20261108T104052Z` | Dress rehearsal |
| `gladi-path-20261108T111639Z` | Path check |
| `gladi3-derp-20261109T083611Z` | Trial 3 (DERP) |
| `gladi4-starlink-20261109T195032Z` | Trial 4 (Starlink direct) |
| `rrtrial-starlink-20261109T214143Z` | Round-robin trial |
| `uplink5x5-starlink-20261109T203631Z` | 5×5 uplink test — **also present at the top level**; this copy is retained for completeness |

## Algorithms / flows

Uplink/downlink logs are organized per congestion-control algorithm (`indigo`, `pcc`, `taova`, `vivace`, and reference `_refNN_cubic`). Files are gzipped raw data-link/ack-link logs.

## Notes

- Data was collected over Starlink; some early trial directories are marked "TIDAK-SAH" (invalid) in the source collection scripts.
- Duplicated `uplink5x5-...` data inside `mentah/` was removed during repo preparation; the top-level copy is authoritative.
