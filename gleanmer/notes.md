# Title: Gleanmer: A 6 mW SoC for Real-Time 3D Gaussian Occupancy Mapping
# Authors: Fu*, Li* (equal contribution), Karaman, Sze (MIT LEAN/EEMS group)
# Link(s): https://arxiv.org/abs/2603.29005 (IEEE VLSI-Circuits 2026) | https://lean.mit.edu/extended-papers/gleanmer
#   Related algorithm paper (GMMap): https://arxiv.org/abs/2306.03740 | local: gleanmer/gmmap.pdf
# Backend / estimator: NOT a VIO/SLAM pose estimator -- this is a 3D occupancy MAPPING chip (Gaussian-based
#   scene representation), built on the GMMap algorithm. Important distinction from Navion/cortex/QVIO2/SurfSLAM,
#   which all estimate pose. Gleanmer maps the environment given known/streamed depth images, on a 16nm SoC.
# What's quantized (if anything):
#   - Gaussian parameters (non-covariance): reduced from 32-bit to 19-bit -- yields 38% area reduction in
#     Fusion + Regression Engine (line ~53)
#   - Covariance matrices: deliberately KEPT at 32-bit "to prevent degeneracy" (line ~54) -- i.e. covariance
#     is treated as precision-sensitive and NOT reduced, while other parameters are
# Key numbers (with exact source):
#   - 6mW total power; 88-331 fps map construction; 540K-1.3M queries/sec (Abstract, MIT page)
#   - 63%/81% reduction in construction/query energy vs baseline GMMap (Abstract)
#   - 38% accelerator area reduction, 44-63% map size reduction, from the 32->19 bit Gaussian
#     precision cut (while covariance stays 32-bit) (line ~53-57)
#   - >96% map accuracy maintained across office/forest/city test scenes (MIT page, Results)
#   - 341x less power than Jetson TX2, 44x less than prior ASIC (OMU) at comparable accuracy (MIT page)
# How it relates to cortex's posit/cfloat covariance study:
#   Strong independent data point: GLEANMER's own hardware team chose to isolate covariance from
#   their general precision-reduction strategy, explicitly citing degeneracy risk -- same instinct
#   as cortex's CovT/T split (state vs covariance get separate types). This is now the SECOND paper
#   (after Navion) whose designers treat covariance/precision-sensitive matrices as needing more bits
#   than other pipeline data. Worth citing alongside Navion's "single precision insufficient" finding
#   when framing why cortex studies covariance precision specifically rather than whole-pipeline precision.
# Open questions / things to verify:
#   - Confirm whether "19-bit" is a custom fixed-point/float format or something like bfloat-adjacent --
#     not explicitly stated in the excerpt pulled so far
#   - Note: this is NOT a VIO paper -- do not describe it to Theo as being in the same category as
#     Navion/QVIO2/SurfSLAM without this caveat
