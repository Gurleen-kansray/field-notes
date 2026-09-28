# VIO benchmark — /mnt/d/work/data/vicon_room1/vicon_room1/V1_01_easy/asl/mav0

**Verdict:** ✅ OK — ATE 0.288766 m within gate 0.5 m.

## Estimator health

| Check | Value |
|---|---|
| Init method | `static` |
| Platform tilt at init (deg) | 112.181 |
| Init gravity residual | 0.00183561 |
| Camera↔IMU extrinsics | set |
| Peak speed (m/s) | 1.06927 |
| Max position norm (m) | 5.424 |

## Accuracy

| Metric | Value |
|---|---|
| ATE (m) | 0.288766 (gate 0.5) |
| RPE RMSE (m) | 0.293602 |
| RPE translation (%) | 16.6846 |
| RPE rotation (deg/m) | 3.13126 |

## Performance

| Metric | Value |
|---|---|
| Frames | 2912 |
| Real-time factor | 0.763489× |
| Throughput (fps) | 15.275 |
| Latency p50 / p99 (ms) | 41.9825 / 63.9301 |

## Energy (empirical — rapl)

_RAPL unavailable (no powercap zones, or `energy_uj` not readable — often root-only since CVE-2020-8694). Run with energy-read access for J/W._

## Operator profile (first-order; Phase-2 graphs energy input)

| Stage | GFLOPs | MB moved |
|---|---|---|
| pyramid | 16.5551 | 2759.18 |
| fast | 16.8178 | 1051.12 |
| klt | 37.3814 | 4672.68 |
| msckf_propagate | 30.6825 | 1519.44 |
| msckf_update | 8.66813 | 706.523 |

