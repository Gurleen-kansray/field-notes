# VIO benchmark — /mnt/d/work/data/vicon_room1/vicon_room1/V1_01_easy/asl/mav0

**Verdict:** ❌ DIVERGED at frame 234 (t=1.40372e+09 s) — peak speed 142.758 m/s, |pos| up to 494.124 m. Metrics below are not meaningful.

## Estimator health

| Check | Value |
|---|---|
| Init method | `static` |
| Platform tilt at init (deg) | 112.181 |
| Init gravity residual | 0.0018357 |
| Camera↔IMU extrinsics | set |
| Peak speed (m/s) | 142.758 |
| Max position norm (m) | 494.124 |

## Accuracy

| Metric | Value |
|---|---|
| ATE (m) | 136.265 (gate 0.5) |
| RPE RMSE (m) | 56.4556 |
| RPE translation (%) | 19030.4 |
| RPE rotation (deg/m) | 336.828 |

## Performance

| Metric | Value |
|---|---|
| Frames | 300 |
| Real-time factor | 0.849783× |
| Throughput (fps) | 17.0525 |
| Latency p50 / p99 (ms) | 33.0313 / 63.2045 |

## Energy (empirical — rapl)

_RAPL unavailable (no powercap zones, or `energy_uj` not readable — often root-only since CVE-2020-8694). Run with energy-read access for J/W._

## Operator profile (first-order; Phase-2 graphs energy input)

| Stage | GFLOPs | MB moved |
|---|---|---|
| pyramid | 1.70554 | 284.256 |
| fast | 1.73261 | 108.288 |
| klt | 3.9204 | 490.05 |
| msckf_propagate | 2.92702 | 148.579 |
| msckf_update | 0.852432 | 71.6387 |

