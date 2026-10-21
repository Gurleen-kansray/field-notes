# VIO benchmark — /mnt/d/work/data/vicon_room1/vicon_room1/V1_03_difficult/asl/mav0

**Verdict:** ✅ OK — ATE 0.208384 m within gate 0.5 m.

## Estimator health

| Check | Value |
|---|---|
| Init method | `static` |
| Platform tilt at init (deg) | 111.858 |
| Init gravity residual | 0.00203076 |
| Camera↔IMU extrinsics | set |
| Peak speed (m/s) | 2.04866 |
| Max position norm (m) | 4.32316 |

## Accuracy

| Metric | Value |
|---|---|
| ATE (m) | 0.208384 (gate 0.5) |
| RPE RMSE (m) | 0.214062 |
| RPE translation (%) | 18.1014 |
| RPE rotation (deg/m) | 2.91709 |

## Performance

| Metric | Value |
|---|---|
| Frames | 2149 |
| Real-time factor | 0.968395× |
| Throughput (fps) | 19.3769 |
| Latency p50 / p99 (ms) | 33.8681 / 44.428 |

## Energy (empirical — rapl)

_RAPL unavailable (no powercap zones, or `energy_uj` not readable — often root-only since CVE-2020-8694). Run with energy-read access for J/W._

## Operator profile (first-order; Phase-2 graphs energy input)

| Stage | GFLOPs | MB moved |
|---|---|---|
| pyramid | 12.2173 | 2036.22 |
| fast | 12.4112 | 775.703 |
| klt | 24.2685 | 3033.56 |
| msckf_propagate | 22.5815 | 1119.38 |
| msckf_update | 5.8859 | 471.593 |

