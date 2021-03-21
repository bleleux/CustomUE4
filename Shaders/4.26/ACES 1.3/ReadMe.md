Modified shaders to include the gamut compression functions from the ACES 1.3 Release Candidate #1: https://github.com/ampas/aces-dev/blob/v1.3_rc1/transforms/ctl/lmt/LMT.Academy.GamutCompress.ctl

The compression is applied in TonemapCommon to AP0 in the FilmToneMap function. It is used in PostProcessCombineLUTs with Blue Correction disabled. The fake wide gamut feature is still enabled, but should be set to 0 in the post-process for an accurate comparison of the gamut compression.

The compression functions include parameters for the threshold and limit of the affected areas, but they are not hooked up in the editor UI as that would require re-compiling the editor. They're easily modifiable in the shader though.
