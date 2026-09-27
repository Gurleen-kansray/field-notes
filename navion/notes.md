# Title: Navion: A 2mW Fully Integrated Real-Time Visual-Inertial Odometry Accelerator for Autonomous Navigation of Nano Drones
# Authors: Suleiman, Zhang, Carlone, Karaman, Sze (MIT EEMS group)
# Link(s): https://arxiv.org/abs/1809.05780 (JSSC 2019 version) | local PDF: navion/navion.pdf
# Backend / estimator: Custom ASIC (65nm CMOS) running non-linear factor graph VIO optimization; EuRoC dataset, stereo 752x480 @ 20fps, 2mW
# What's quantized (if anything):
#   - Arithmetic precision: BE (back-end) and IFE (IMU front-end) use DOUBLE PRECISION throughout, explicitly stated
#     because single precision does not provide sufficient numerical precision for the solve (line ~297-300 of extracted text)
#   - Separate axis, NOT arithmetic: pixel/image memory compression via block quantization
#     (4x4 blocks quantized to 1-bit/pixel via LSB truncation + per-block dynamic range, 5-bit pixel quantization)
#     used to reduce on-chip memory size 4.1x -- this is data compression, not solver precision
# Key numbers (with exact source):
#   - 4.1x on-chip memory reduction via structured+unstructured sparsity (Abstract)
#   - 43% throughput increase via parallelism (Abstract)
#   - 2mW average power at 20fps real-time on EuRoC; peak 171fps/24mW (Abstract)
#   - 85 double-precision registers in shared register file (line ~326)
#   - Memory optimization: replaced 64-bit double-precision 3D coordinates with a two-stage
#     memory architecture to shrink a 40,000-entry landmark table (line ~369-370)
# How it relates to cortex's posit/cfloat covariance study:
#   Most directly relevant paper found so far -- Navion is a real hardware team that tried
#   dropping below double precision for the VIO solve itself and explicitly rejected single
#   precision as insufficient. Worth flagging to Theo: their memory-side quantization (pixel/
#   landmark storage) is a different axis from covariance-arithmetic precision, but their
#   "double precision needed, single precision insufficient" finding is a real prior data point
#   that cortex's posit<32,2>/cfloat sweep could either confirm or complicate (posits at n=32
#   sit in different tradeoff space than IEEE single/float32, since quire-based accumulation
#   changes the accuracy story)
# Open questions / things to verify:
#   - Confirm exactly which part of the pipeline "single precision insufficient" was tested on
#     (full BE solve, or a specific sub-step) -- worth a closer read of surrounding text (~line 250-300)
#   - Check if there's a public repo/software release (the lean.mit.edu page mentions "Software" link)
