# VIO benchmark — /mnt/d/work/data/vicon_room1/vicon_room1/V1_02_medium/asl/mav0

**Verdict:** ✅ OK — ATE 0.150796 m within gate 0.5 m.

## Estimator health

| Check | Value |
|---|---|
| Init method | `static` |
| Platform tilt at init (deg) | 109.046 |
| Init gravity residual | 0.00120007 |
| Camera↔IMU extrinsics | set |
| Peak speed (m/s) | 2.16529 |
| Max position norm (m) | 4.59618 |

## Accuracy

| Metric | Value |
|---|---|
| ATE (m) | 0.150796 (gate 0.5) |
| RPE RMSE (m) | 0.109431 |
| RPE translation (%) | 5.28858 |
| RPE rotation (deg/m) | 0.961515 |

## Performance

| Metric | Value |
|---|---|
| Frames | 1710 |
| Real-time factor | 1.02522× |
| Throughput (fps) | 20.5165 |
| Latency p50 / p99 (ms) | 34.9811 / 41.0751 |

## Energy (empirical — rapl)

_RAPL unavailable (no powercap zones, or `energy_uj` not readable — often root-only since CVE-2020-8694). Run with energy-read access for J/W._

## Operator profile (first-order; Phase-2 graphs energy input)

| Stage | GFLOPs | MB moved |
|---|---|---|
| pyramid | 9.72156 | 1620.26 |
| fast | 9.87587 | 617.242 |
| klt | 21.994 | 2749.25 |
| msckf_propagate | 17.9073 | 888.544 |
| msckf_update | 5.0729 | 414.525 |

