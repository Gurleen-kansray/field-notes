# VIO benchmark — /mnt/d/work/data/vicon_room1/vicon_room1/V1_01_easy/asl/mav0

**Verdict:** ✅ OK — ATE 0.0654543 m within gate 0.5 m.

## Estimator health

| Check | Value |
|---|---|
| Init method | `static` |
| Platform tilt at init (deg) | 112.181 |
| Init gravity residual | 0.00183561 |
| Camera↔IMU extrinsics | set |
| Peak speed (m/s) | 0.451704 |
| Max position norm (m) | 1.33928 |

## Accuracy

| Metric | Value |
|---|---|
| ATE (m) | 0.0654543 (gate 0.5) |
| RPE RMSE (m) | 0.0732334 |
| RPE translation (%) | 1771.14 |
| RPE rotation (deg/m) | 76.6085 |

## Performance

| Metric | Value |
|---|---|
| Frames | 300 |
| Real-time factor | 0.836992× |
| Throughput (fps) | 16.7958 |
| Latency p50 / p99 (ms) | 34.5872 / 91.0555 |

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

