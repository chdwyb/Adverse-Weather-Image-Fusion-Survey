# Evaluating fusion quality

[Home](../README.md) · [Public implementations](implementations.md)

A common metric suite is useful **within a common observation and output contract**. A fused visible/thermal display, a 13-band optical reconstruction, a high-resolution multispectral image, and a semantic prediction cannot be ranked reliably by one scalar. Shared terms such as PSNR or SSIM also require the same reference, range, spectral channels, support, and aggregation.

## Choose metrics by output domain

| Output | Core quality dimensions | Appropriate measurements | Essential qualification |
| :-- | :-- | :-- | :-- |
| VIS–infrared fused display | Source structure and information; introduced artifacts; task utility | Q_AB/F, fusion VIFF, feature mutual information, an artifact measure; optional fixed downstream evaluation | These source-based metrics do not provide an ideal clean fused target. Corrupted edges can be rewarded. |
| SAR-assisted optical reconstruction | Spatial and radiometric fidelity; spectral fidelity; cloud-region recovery | PSNR, SSIM, SAM; region-stratified errors | Compare against a declared optical reference; account for changes between acquisition dates. |
| PAN–MS or HS–MS/PAN fusion | Spectral preservation and spatial detail | SAM, ERGAS, PSNR/SSIM under reduced-resolution references; QNR-family measures at full resolution | Full-resolution no-reference measures and reduced-resolution reference measures answer different questions. |
| Fused-feature perception | Semantic or geometric prediction; failure behavior | mIoU for semantic segmentation; AP/mAP for detection; task-appropriate depth/uncertainty metrics | Match sensors, backbone, supervision, resolution, pretraining, and label space. Task scores alone do not certify image fidelity. |

## Metric definitions and implementation identity

| Resource | What it contributes |
| :-- | :-- |
| [Objective image fusion performance measure](https://doi.org/10.1049/el:20000267) | Edge information preservation (Q_AB/F). |
| [A new image fusion performance metric based on visual information fidelity](https://doi.org/10.1016/j.inffus.2011.08.002) | Fusion-specific visual information fidelity with its prescribed multiscale/subband weighting. |
| [A Non-Reference Image Fusion Metric Based on Mutual Information of Image Features](https://doi.org/10.1016/j.compeleceng.2011.07.012) | Feature mutual information for non-reference fusion assessment. |
| [Fast-FMI: Non-reference image fusion metric](https://doi.org/10.1109/ICAICT.2014.7036000) | Efficient FMI implementation; the feature representation must be specified. |
| [A human perception inspired quality metric for image fusion based on regional information](https://doi.org/10.1016/j.inffus.2005.10.001) | Regional information and human-perception-based fusion assessment. |
| [A new automated quality assessment algorithm for image fusion](https://doi.org/10.1016/j.imavis.2007.12.002) | Perceptual fusion-quality assessment with explicit source/fused relationships. |
| [Subjective tests for image fusion evaluation and objective metric validation](https://doi.org/10.1016/j.inffus.2005.05.001) | Subjective evaluation and the validation of objective metrics. |
| [Image Quality Assessment: From Error Visibility to Structural Similarity](https://doi.org/10.1109/TIP.2003.819861) | Structural similarity for comparable reference images. |
| [The Spectral Image Processing System (SIPS)—Interactive Visualization and Analysis of Imaging Spectrometer Data](https://doi.org/10.1016/0034-4257(93)90013-N) | Spectral-angle assessment of spectral shape. |
| [Data Fusion: Definitions and Architectures—Fusion of Images of Different Spatial Resolutions](https://hal.science/hal-00464703) | Spatial–spectral fusion evaluation and scale-aware error. |
| [Multispectral and Panchromatic Data Fusion Assessment Without Reference](https://doi.org/10.14358/PERS.74.2.193) | No-reference spectral and spatial distortion assessment. |
| [The Unreasonable Effectiveness of Deep Features as a Perceptual Metric](https://openaccess.thecvf.com/content_cvpr_2018/html/Zhang_The_Unreasonable_Effectiveness_CVPR_2018_paper.html) | Learned perceptual similarity; its training domain must suit the evaluated output. |

The name **VIFF** is not sufficient to identify an implementation. Summing two ordinary pairwise VIF scores is not automatically the fusion-specific metric of Han et al. Similarly, FMI_pixel, FMI_DCT, and wavelet FMI should not be conflated. Record the actual function, feature transform, numerical range, boundary handling, and aggregation.

Useful public resources include the [author FMI implementation](https://github.com/mhaghighat/fmi), [VIFB](https://github.com/xingchenzhang/VIFB), and [DLPan-Toolbox](https://github.com/liangjiandeng/DLPan-Toolbox). Benchmark collections are starting points; verify their metric definitions against the primary papers before combining results.

## A reproducible comparison checklist

1. **Fix the information budget.** Declare measured sensors, acquisition dates, prompts, masks, generated auxiliaries, and training-only annotations.
2. **Fix the output contract.** Specify channels, physical units or numerical range, luminance/color conversion, clipping, and image support.
3. **Use valid references.** Distinguish measured clean observations, pre-corruption sources, other-date optical images, synthetic targets, and algorithmic pseudo-references.
4. **Stratify the conditions.** Report weather type and severity, real versus synthetic acquisition, alignment quality, and missing/degraded sensors.
5. **Respect dependence.** Split and aggregate by independent scene, sequence, region, or source image; synthetic variants of one scene are not independent samples.
6. **Report complementary evidence.** Show source preservation, artifacts, spectral/radiometric fidelity when applicable, and task utility instead of selecting one favorable score.
7. **Account for the whole system.** Include preprocessing, auxiliary models, sampling steps, prompts, and output conversion in cost and reproducibility descriptions.

A method can score highly against a weather-corrupted source while retaining the corruption. Conversely, suppressing weather can lower a source-similarity score. Inspection against valid references and independent task or spectral evidence is therefore needed to interpret the numbers.
