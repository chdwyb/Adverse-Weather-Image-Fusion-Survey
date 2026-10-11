# Public implementations and configuration boundaries

[Home](../README.md) · [Method catalogue](methods.md) · [Evaluation](evaluation.md)

This page identifies substantive public implementation resources and qualifications. It is not a claim that every linked configuration can be executed without adaptation, that all weights are downloadable, or that published results have been reproduced. The complete literature list includes methods for which no implementation link has been verified.

## Visible–infrared image fusion

| Method | Public source | Implementation and input boundary |
| :-- | :-- | :-- |
| GFF / GTF | [Author-attributed MATLAB source](https://github.com/jiayi-ma/GTF) | Analytical filtering/optimization; no training or checkpoint is required. Select each core routine and record its numerical settings. |
| SwinFusion | [Author repository](https://github.com/Linfeng-Tang/SwinFusion) | Training and inference source. Use the intended two-input path; tiled and full-image paths require separate interface checks. |
| CDDFuse | [Author repository](https://github.com/Zhaozixiang1228/MMIF-CDDFuse) | Training, inference, and fusion model. Match the evaluator to the chosen metric definition. |
| SeAFusion | [Author repository](https://github.com/Linfeng-Tang/SeAFusion) | Training and inference source; semantic supervision during training. Document native color reconstruction. |
| STDFusionNet | [Author repository](https://github.com/Linfeng-Tang/STDFusionNet) | Saliency masks guide training losses; the fusion network consumes the two images at inference. Legacy dependencies require attention. |
| TarDAL | [Author repository](https://github.com/JinyuanLiu-CV/TarDAL) | Select the intended CT/DT recipe and weights. Fusion-only prediction differs from detector visualization, and dataset loaders can impose unrelated label requirements. |
| Text-IF | [Author repository](https://github.com/XunpengYi/Text-IF) | Text-conditioned fusion with distinct released settings. Record prompt policy and actual training/degradation coverage. |
| TG-ECNet | [Author repository](https://github.com/LeeX54946/TG-ECNet) | Degradation/text configuration and any auxiliary description inputs must be disclosed. |
| DDFM | [Author repository](https://github.com/Zhaozixiang1228/MMIF-DDFM) | Diffusion-based fusion. Pin the prior, conditioning path, and sampling schedule. |
| DRMF | [Author repository](https://github.com/Linfeng-Tang/DRMF) | Restoration and fusion stages have separate source paths and priors; account for both. |
| AWFusion | [Author repository](https://github.com/ixilai/AWFusion) | Teacher/student training and testing resources. Distinguish released recipes and compound-weather settings. |
| SegMiF | [Author repository](https://github.com/JinyuanLiu-CV/SegMiF) | Public inference code uses external mask files; their provenance and inference-time availability must be resolved for a strict two-observation comparison. |
| MetaFusion | [Author repository](https://github.com/wdzhao123/MetaFusion) | An inference release is available; a complete training entry point was not established by the inspected source. |

## SAR–optical cloud reconstruction

| Method | Public source | Implementation and input boundary |
| :-- | :-- | :-- |
| DSen2-CR | [Author repository](https://github.com/ameraner/dsen2-cr) | Mono-temporal SAR+MS and MS-only alternatives. Preserve the selected input configuration and maintainer dependency notes. |
| GLF-CR | [Author repository](https://github.com/xufangchn/GLF-CR) | Training and inference; custom CUDA components, patching, and tiling require matching. |
| UnCRtainTS | [Author repository](https://github.com/PatrickTUM/UnCRtainTS) | Temporal length and SAR use are configuration choices. A three-date checkpoint is not interchangeable with a single-date model. |
| TASANet | [Author repository](https://github.com/ningjin00/TASANet) | Training/prediction source separates two SAR and 13 optical channels. Check compatible weight retrieval. |
| EMRDM | [Author repository](https://github.com/Ly403/EMRDM) | The Sentinel configuration combines noisy optical, observed optical, and SAR. The noisy diffusion state is not an additional measured sensor. |

The original DiffCR formulation uses optical temporal observations. A later SAR–optical extension should be identified as a distinct configuration rather than silently attributed to the original input contract.

## Spatial–spectral fusion

| Resource | Public source | Implementation and input boundary |
| :-- | :-- | :-- |
| PNN, PanNet, DiCNN, MSDCNN, BDPN, FusionNet | [DLPan-Toolbox](https://github.com/liangjiandeng/DLPan-Toolbox) | Third-party benchmark implementations with shared training/testing runners. Match sensor channels, preprocessing, and spatial ratio; weights for different sensors are not interchangeable. |
| GSA / MTF-GLP-HPM | [DLPan benchmark distribution](https://github.com/liangjiandeng/DLPan-Toolbox) | Analytical MATLAB baselines. State the selected variant and sensor MTF assumptions. |
| LRTCFPan | [Author repository](https://github.com/zhongchengwu/code_LRTCFPan) | MATLAB optimization implementation; no learned checkpoint required. |
| Pan-TCR | [Author repository](https://github.com/dusongcheng/PanTCR-GF2) | Public training/test source; a validation-call argument mismatch requires a documented mechanical repair. |

## Multimodal perception

| System | Public source | Configuration boundary |
| :-- | :-- | :-- |
| CMNeXt / DeLiVER | [Author repository](https://github.com/InSAI-Lab/DELIVER) | RGB, depth, LiDAR, and event configurations are explicit. Depth may be represented as HHA. |
| GeminiFusion | [Author DeLiVER branch](https://github.com/JiaDingCN/GeminiFusion/tree/DeLiVER) | Use the matching four-input branch and configuration; the main branch targets other RGB-D datasets. |
| CAFuser | [Author repository](https://github.com/timbroed/CAFuser) | Multiple sensor subsets and condition-aware settings exist. Report the exact modalities, backbone, auxiliary condition information, training labels, and checkpoint. A family name is not a fully specified baseline. |
| MUSES | [Dataset SDK](https://github.com/timbroed/MUSES) | The SDK provides data handling and evaluation resources; it is not a released fusion-model training pipeline. |

## Before interpreting code availability

Distinguish **analytical implementation**, **training and inference code**, **inference-only release**, **model definitions only**, **data SDK**, and **project announcement**. Pin a commit and configuration, identify externally required inputs, record weight provenance, and check data/weight licenses independently. Do not infer experimental eligibility from a repository badge or paper-level method name.
