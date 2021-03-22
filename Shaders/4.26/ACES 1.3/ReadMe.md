Modified shaders to include the gamut compression functions from the ACES 1.3 Release Candidate #1: https://github.com/ampas/aces-dev/blob/v1.3_rc1/transforms/ctl/lmt/LMT.Academy.GamutCompress.ctl

The compression is applied in TonemapCommon to the AP0 color in the FilmToneMap function. It is used in PostProcessCombineLUTs where the blue correction and fake wide gamut are disabled.

The compression functions include parameters for the threshold and limit of the affected areas, but they are not hooked up in the editor UI as that would require re-compiling the editor. They're easily modifiable in the shader though.
