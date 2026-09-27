# Title: SurfSLAM: Sim-to-Real Underwater Stereo Reconstruction For Real-Time SLAM
# Authors: Bagoren, Isaacson, Sundar, Sun, Sheppard, Ma, Shariff, Vasudevan, Skinner (Michigan Field Robotics)
# Link(s): https://umfieldrobotics.github.io/SurfSLAM/  |  local PDF: surfslam/surfslam.pdf
# Backend / estimator: Custom real-time SLAM framework fusing stereo + IMU + DVL + barometer for pose tracking
# What's quantized (if anything): None — this is a sim-to-real depth estimation problem, not a precision/quantization study
# Key numbers (with exact source — page/table):
#   - 24,000+ stereo pairs in their own shipwreck-survey dataset (p.1, Introduction)
#   - Dataset includes reference 3D reconstructions + ground-truth vehicle pose (p.1-2)
#   - No ATE/quantitative accuracy numbers found via grep yet — check Experiments section directly if needed
# How it relates to cortex's posit/cfloat covariance study:
#   Not a quantization axis at all — orthogonal to cortex. Relevant to "tracking the field" only
#   as an example of SLAM robustness work outside standard datasets (EuRoC/TUM), and as a
#   contrast: shows what non-quantization SLAM research looks like vs QVIO2's actual quantization work
# Open questions / things to verify:
#   - Pull actual ATE/trajectory error numbers from Experiments/Results section if useful
#   - Confirm which backend/estimator family this builds on (custom, not explicitly MSCKF-based like cortex)
