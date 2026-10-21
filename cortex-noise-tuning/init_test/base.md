# VIO benchmark — /mnt/d/work/data/vicon_room1/vicon_room1/V1_01_easy/asl/mav0

**Verdict:** ✅ OK — ATE 0.173367 m within gate 0.5 m.

## Estimator health

| Check | Value |
|---|---|
| Init method | `static` |
| Platform tilt at init (deg) | 112.181 |
| Init gravity residual | 0.00183561 |
| Camera↔IMU extrinsics | set |
| Peak speed (m/s) | 0.996737 |
| Max position norm (m) | 5.45932 |

## Accuracy

| Metric | Value |
|---|---|
| ATE (m) | 0.173367 (gate 0.5) |
| RPE RMSE (m) | 0.231971 |
| RPE translation (%) | 11.8206 |
| RPE rotation (deg/m) | 2.18978 |

## Performance

| Metric | Value |
|---|---|
| Frames | 2912 |
| Real-time factor | 0.901702× |
| Throughput (fps) | 18.0402 |
| Latency p50 / p99 (ms) | 36.5515 / 46.6711 |

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

