# Adverse-Weather Image Fusion Survey

A curated collection of **multimodal fusion methods, datasets, public implementations, and evaluation resources** for adverse weather.

Rain, fog, haze, snow, and cloud cover affect sensors differently. This resource follows how complementary observations are combined across **visible, thermal and near-infrared, multispectral, hyperspectral, panchromatic, SAR, LiDAR, radar, and event** sensing. It covers image formation and task-oriented feature fusion while keeping their output domains distinct.

**132 method records · 51 dataset and resource entries · primary publication links · implementation qualifications**

## Navigation

- [Scope and taxonomy](#scope-and-taxonomy)
- [Papers by year](#papers-by-year)
- [Methods by fusion mechanism](docs/methods.md)
- [Datasets and benchmarks](#datasets-and-benchmarks) · [full inventory](docs/datasets.md)
- [Public implementations](docs/implementations.md)
- [Evaluation resources](docs/evaluation.md)
- [Research directions](#research-directions)
- [Contributing](#contributing)

## Scope and taxonomy

The literature includes several distinct output contracts: a fused display image, an optical reconstruction from complementary sensors, a spatially enhanced spectral image, or a prediction obtained from fused features. Their observation budgets and evaluation targets should be stated explicitly.

The primary categories describe **how the estimate is produced**:

| Primary family | Operational boundary |
| :-- | :-- |
| **M — Model-derived inference** | Analytical fusion, optimization, or a learned architecture explicitly derived from an observation model or optimization procedure. |
| **D — Direct learned estimation** | A trained forward mapping predicts a fused image, reconstructed signal, or task representation without iterative distributional sampling at inference. |
| **G — Iterative generative estimation** | Diffusion, flow, or another iterative distributional reconstruction process produces the estimate. |

**Conditioning** and **task guidance** are additional attributes, not competing primary categories. A direct estimator can use prompts or semantic supervision; a generative estimator can be physically constrained and task guided. Adversarial training alone does not make a deterministic forward network an iterative generative estimator. See the [method map](docs/methods.md) for assignments and hybrid attributes.

**Weather** marks an explicit weather-related formulation or evaluation in the cited source. **Foundation** marks a general fusion method, an adjacent degradation setting, or a comparison control; it does not imply demonstrated weather robustness. Nighttime and low illumination are not automatically weather. Near-infrared and thermal infrared, radar and SAR, and measured and synthesized auxiliary modalities remain distinct.

## Papers by year

Entries use the formal publication year where verified; preprints are labeled separately. This is a curated reading list, not a census of all publications. A source-code link does not by itself establish a complete training recipe, compatible weights, or reproducible scores. A dash means that no implementation link is recorded here, not that none exists.


### 2026

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **AGFlow** — Asynchronous Remote Sensing Time-Series Fusion for Cloud Removal and Anytime Reconstruction | Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops | G | Weather | [Paper](https://openaccess.thecvf.com/content/CVPR2026W/MORSE/papers/Fallah_Asynchronous_Remote_Sensing_Time-Series_Fusion_for_Cloud_Removal_and_Anytime_CVPRW_2026_paper.pdf) |
| **AMG-Fuse** — Multi-modality Image Fusion Under Adverse Weather: Mask-Guided Feature Restoration and Interaction | ECCV | D | Weather | [Paper](https://doi.org/10.1007/978-3-032-37602-2_7) · [Source](https://github.com/ixilai/AMG-Fuse) |
| **AWFusion** — All-weather Multi-Modality Image Fusion: Unified Framework and 100k Benchmark | Information Fusion | M | Weather | [Paper](https://doi.org/10.1016/j.inffus.2026.104130) · [Source](https://github.com/ixilai/AWFusion) |
| **AWM-Fuse** — AWM-Fuse: Multi-Modality Image Fusion for Adverse Weather via Global and Local Text Perception | TIP | D | Weather | [Paper](https://doi.org/10.1109/TIP.2026.3690324) · [Source](https://github.com/Feecuin/AWM-Fuse) |
| **CAWM-Mamba** — CAWM-Mamba: A unified model for infrared-visible image fusion and compound adverse weather restoration | Expert Systems with Applications | D | Weather | [Paper](https://doi.org/10.1016/j.eswa.2026.131665) · [Source](https://github.com/Feecuin/CAWM-Mamba) |
| **DACDM-CR** — DACDM-CR: Discriminative attention and cloud-aware dynamic mamba for SAR-assisted optical data cloud removal | Digital Signal Processing | D | Weather | [Paper](https://doi.org/10.1016/j.dsp.2025.105522) |
| **Data-interactive Mamba** — Data-interactive mamba driven SAR-optical fusion cloud removal | Knowledge-Based Systems | D | Weather | [Paper](https://doi.org/10.1016/j.knosys.2026.115301) |
| **DGFusion** — DGFusion: Depth-Guided Sensor Fusion for Robust Semantic Perception | IEEE Robotics and Automation Letters | D | Weather | [Paper](https://doi.org/10.1109/lra.2026.3656789) · [Source](https://github.com/timbroed/DGFusion) |
| **Doppler-guided cooperative fusion** — 4-D Radar Meets LiDAR and Camera: Cooperative Perception under Adverse Weather | Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops | D | Weather | [Paper](https://openaccess.thecvf.com/content/CVPR2026W/DriveX/html/Yazgan_4-D_Radar_Meets_LiDAR_and_Camera_Cooperative_Perception_under_Adverse_CVPRW_2026_paper.html) |
| **DRFusion** — Degradation-Robust Fusion: An Efficient Degradation-Aware Diffusion Framework for Multimodal Image Fusion in Arbitrary Degradation Scenarios | CVPR | G | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2026/html/Shi_Degradation-Robust_Fusion_An_Efficient_Degradation-Aware_Diffusion_Framework_for_Multimodal_Image_CVPR_2026_paper.html) · [Source](https://github.com/YShi-cool/DRFusion) |
| **DSPFusion** — DSPFusion: Image Fusion via Degradation and Semantic Dual-Prior Guidance | TIP | G | Weather | [Paper](https://doi.org/10.1109/TIP.2026.3700938) · [Source](https://github.com/Linfeng-Tang/DSPFusion) |
| **GLCdiffcr** — A global-local interaction and conditional consistency constrained diffusion model for SAR-guided optical image cloud removal | International Journal of Applied Earth Observation and Geoinformation | G | Weather | [Paper](https://doi.org/10.1016/j.jag.2025.105013) |
| **HRCP** — Hybrid Robust Collaborative Perception with LiDAR-4D Radar Fusion under Adverse Weather Conditions | Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition | D | Weather | [Paper](https://openaccess.thecvf.com/content/CVPR2026/papers/Yang_Hybrid_Robust_Collaborative_Perception_with_LiDAR-4D_Radar_Fusion_under_Adverse_CVPR_2026_paper.pdf) |
| **IASSF** — Infrared-assisted single-stage framework for joint restoration and fusion of visible and infrared images under hazy conditions | Pattern Recognition | D | Weather | [Paper](https://doi.org/10.1016/j.patcog.2026.113074) · [Source](https://github.com/fangjiaqi0909/IASSF) |
| **Mamba-SCR** — Mamba-SCR: a frequency-domain enhanced state space model for cloud removal with SAR and optical data fusion | GIScience & Remote Sensing | D | Weather | [Paper](https://doi.org/10.1080/15481603.2026.2677334) |
| **Mask-DiFuser** — Mask-DiFuser: A Masked Diffusion Model for Unified Unsupervised Image Fusion | TPAMI | G | Foundation | [Paper](https://doi.org/10.1109/TPAMI.2025.3609323) |
| **MdaIF** — MdaIF: Robust One-Stop Multi-Degradation-Aware Image Fusion with Language-Driven Semantics | AAAI | D | Weather | [Paper](https://doi.org/10.1609/aaai.v40i8.37548) |
| **NAM-CR** — NAM-CR: Noise-aware multisensor cloud removal for optical remote sensing imagery by fusing SAR data | Information Fusion | D | Weather | [Paper](https://doi.org/10.1016/j.inffus.2026.104295) |
| **Pan-TCR** — Pansharpening for Thin-Cloud Contaminated Remote Sensing Images: A Unified Framework and Benchmark Dataset | AAAI | D | Weather | [Paper](https://doi.org/10.1609/aaai.v40i5.37369) · [Source](https://github.com/dusongcheng/PanTCR-GF2) |
| **PMNet** — PMNet: A Positional Mamba Network for SAR-Assisted Cloud Removal | GRSL | D | Weather | [Paper](https://doi.org/10.1109/lgrs.2026.3726690) |
| **ReCoFuse** — ReCoFuse: Ultra-Robust Image Fusion via Restorative Multi-Modal Diffusion Reciprocal Coupling | CVPR | G | Weather | [Paper](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_ReCoFuse_Ultra-Robust_Image_Fusion_via_Restorative_Multi-Modal_Diffusion_Reciprocal_Coupling_CVPR_2026_paper.html) · [Source](https://github.com/HaoZhang1018/ReCoFuse) |
| **VideoFusion** — VideoFusion: A Spatio-Temporal Collaborative Network for Multi-modal Video Fusion | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2026/html/Tang_VideoFusion_A_Spatio-Temporal_Collaborative_Network_for_Multi-modal_Video_Fusion_CVPR_2026_paper.html) |

### 2025

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **C2RF** — C2RF: Bridging Multi-modal Image Registration and Fusion via Commonality Mining and Contrastive Learning | IJCV | D | Foundation | [Paper](https://doi.org/10.1007/s11263-025-02427-1) |
| **CAFuser** — CAFuser: Condition-Aware Multimodal Fusion for Robust Semantic Perception of Driving Scenes | IEEE Robotics and Automation Letters | D | Weather | [Paper](https://doi.org/10.1109/lra.2025.3536218) · [Source](https://github.com/timbroed/CAFuser) |
| **CFMW** — CFMW: Cross-Modality Fusion Mamba for Robust Object Detection Under Adverse Weather | TCSVT | D | Weather | [Paper](https://doi.org/10.1109/TCSVT.2025.3587918) · [Source](https://github.com/lhy-zju/CFMW) |
| **ControlFusion** — ControlFusion: A Controllable Image Fusion Network with Language-Vision Degradation Prompts | NeurIPS | D | Weather | [Paper](https://doi.org/10.52202/085713-3946) · [Source](https://github.com/Linfeng-Tang/ControlFusion) |
| **DAFusion** — A degradation-aware guided fusion network for infrared and visible image | Information Fusion | D | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2025.102931) · [Source](https://github.com/wang-x-1997/DAFusion) |
| **DB-CR** — Multimodal Diffusion Bridge With Attention-Based SAR Fusion for Satellite Image Cloud Removal | TGRS | G | Weather | [Paper](https://doi.org/10.1109/tgrs.2025.3604654) |
| **DLRFusion** — Doppler-Aware LiDAR-RADAR Fusion for Weather-Robust 3D Detection | ICCV | D | Weather | [Paper](https://doi.org/10.1109/iccv51701.2025.02525) |
| **Dual-domain hierarchical fusion** — Breaking through clouds: A hierarchical fusion network empowered by dual-domain cross-modality interactive attention for cloud-free image reconstruction | Information Fusion | D | Weather | [Paper](https://doi.org/10.1016/j.inffus.2024.102649) |
| **EMRDM** — Effective Cloud Removal for Remote Sensing Images by an Improved Mean-Reverting Denoising Model with Elucidated Design Space | CVPR | G | Weather | [Paper](https://doi.org/10.1109/cvpr52734.2025.01663) · [Source](https://github.com/Ly403/EMRDM) |
| **FIVFusion** — FIVFusion: Fog-free infrared and visible image fusion | Journal of King Saud University Computer and Information Sciences | M | Weather | [Paper](https://doi.org/10.1007/s44443-025-00309-7) · [Source](https://github.com/XiangheBi/FIVFusion) |
| **FoggyFuse** — FoggyFuse: Infrared and visible image fusion method based on saturation line prior in foggy conditions | Optics & Laser Technology | M | Weather | [Paper](https://doi.org/10.1016/j.optlastec.2025.113075) |
| **GIFNet** — One Model for ALL: Low-Level Task Interaction Is a Key to Task-Agnostic Image Fusion | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2025/papers/Cheng_One_Model_for_ALL_Low-Level_Task_Interaction_Is_a_Key_CVPR_2025_paper.pdf) |
| **HaIVFusion** — HaIVFusion: Haze-Free Infrared and Visible Image Fusion | IEEE/CAA Journal of Automatica Sinica | D | Weather | [Paper](https://doi.org/10.1109/JAS.2024.124926) |
| **M3-CR** — M3-CR: Multiscale Multibranch Mamba for SAR-Assisted Optical Image Thick Cloud Removal | TGRS | D | Weather | [Paper](https://doi.org/10.1109/tgrs.2025.3566088) |
| **MMAIF** — MMAIF: Multi-task and Multi-degradation All-in-One for Image Fusion with Language Guidance | ICCV | D/G | Weather | [Paper](https://openaccess.thecvf.com/content/ICCV2025/html/Cao_MMAIF_Multi-task_and_Multi-degradation_All-in-One_for_Image_Fusion_with_Language_ICCV_2025_paper.html) · [Source](https://github.com/294coder/MMAIF) |
| **MoME** — Resilient Sensor Fusion under Adverse Sensor Failures via Multi-Modal Expert Fusion | CVPR | D | Weather | [Paper](https://doi.org/10.1109/cvpr52734.2025.00630) |
| **OmniFuse** — OmniFuse: Composite Degradation-Robust Image Fusion With Language-Driven Semantics | TPAMI | G | Foundation | [Paper](https://doi.org/10.1109/TPAMI.2025.3568433) · [Source](https://github.com/HaoZhang1018/OmniFuse) |
| **PODF-CR** — Cloud Removal With PolSAR-Optical Data Fusion Using A Two-Flow Residual Network | arXiv preprint | D | Weather | [Paper](https://doi.org/10.48550/arXiv.2501.07901) |
| **RESTORE-DiT** — RESTORE-DiT: Reliable satellite image time series reconstruction by multimodal sequential diffusion transformer | Remote Sensing of Environment | G | Weather | [Paper](https://doi.org/10.1016/j.rse.2025.114872) |
| **SAG-CR** — Robust SAR-assisted cloud removal via supervised align-guided fusion and bidirectional hybrid reconstruction | International Journal of Digital Earth | D | Weather | [Paper](https://doi.org/10.1080/17538947.2025.2472909) |
| **SAGE** — Every SAM Drop Counts: Embracing Semantic Priors for Multi-Modality Image Fusion and Beyond | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2025/html/Wu_Every_SAM_Drop_Counts_Embracing_Semantic_Priors_for_Multi-Modality_Image_CVPR_2025_paper.html) |
| **SARDiff-CR** — Efficient Diffusion Model for SAR-Assisted Optical Remote Sensing Image Cloud Removal | Proceedings of the IEEE International Geoscience and Remote Sensing Symposium (IGARSS) | G | Weather | [Paper](https://doi.org/10.1109/IGARSS55030.2025.11243696) |
| **SDSFusion** — SDSFusion: A Semantic-Aware Infrared and Visible Image Fusion Network for Degraded Scenes | TIP | D | Foundation | [Paper](https://doi.org/10.1109/TIP.2025.3571339) |
| **TDFusion** — Task-driven Image Fusion with Learnable Fusion Loss | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2025/papers/Bai_Task-driven_Image_Fusion_with_Learnable_Fusion_Loss_CVPR_2025_paper.pdf) |
| **TG-ECNet** — Task-Gated Multi-Expert Collaboration Network for Degraded Multi-Modal Image Fusion | Proceedings of the 42nd International Conference on Machine Learning | D | Weather | [Paper](https://proceedings.mlr.press/v267/sun25k.html) · [Source](https://github.com/LeeX54946/TG-ECNet) |
| **URFusion** — URFusion: Unsupervised Unified Degradation-Robust Image Fusion Network | TIP | D | Foundation | [Paper](https://doi.org/10.1109/TIP.2025.3607628) |

### 2024

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **Align-CR** — Multimodal and Multiresolution Data Fusion for High-Resolution Cloud Removal: A Novel Baseline and Benchmark | TGRS | D | Weather | [Paper](https://doi.org/10.1109/TGRS.2023.3337845) |
| **BA-Fusion** — Dynamic Brightness Adaptation for Robust Multi-modal Image Fusion | Proceedings of the International Joint Conference on Artificial Intelligence (IJCAI) | D | Foundation | [Paper](https://doi.org/10.24963/ijcai.2024/146) |
| **CoCoNet** — CoCoNet: Coupled Contrastive Learning Network with Multi-level Feature Ensemble for Multi-modality Image Fusion | IJCV | D | Foundation | [Paper](https://doi.org/10.1007/s11263-023-01952-1) · [Source](https://github.com/runjia0124/CoCoNet) |
| **CRformer** — CRformer: Multi-modal data fusion to reconstruct cloud-free optical imagery | International Journal of Applied Earth Observation and Geoinformation | D | Weather | [Paper](https://doi.org/10.1016/j.jag.2024.103793) |
| **DiffCR** — DiffCR: A Fast Conditional Diffusion Framework for Cloud Removal From Optical Satellite Images | TGRS | G | Foundation | [Paper](https://doi.org/10.1109/tgrs.2024.3365806) |
| **DRMF** — DRMF: Degradation-Robust Multi-Modal Image Fusion via Composable Diffusion Prior | Proceedings of the ACM International Conference on Multimedia | G | Foundation | [Paper](https://doi.org/10.1145/3664647.3681064) · [Source](https://github.com/Linfeng-Tang/DRMF) |
| **EMMA** — Equivariant Multi-Modality Image Fusion | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2024/html/Zhao_Equivariant_Multi-Modality_Image_Fusion_CVPR_2024_paper.html) · [Source](https://github.com/Zhaozixiang1228/MMIF-EMMA) |
| **FENet** — Feature enhancement network for cloud removal in optical images by fusing with SAR images | International Journal of Remote Sensing | D | Weather | [Paper](https://doi.org/10.1080/01431161.2023.2292014) |
| **FPNet** — Efficient Cloud Removal Network for Satellite Images Using SAR-Optical Image Fusion | GRSL | D | Weather | [Paper](https://doi.org/10.1109/lgrs.2024.3397875) |
| **HDRSA-Net** — HDRSA-Net: Hybrid dynamic residual self-attention network for SAR-assisted optical image cloud and shadow removal | ISPRS Journal of Photogrammetry and Remote Sensing | D | Weather | [Paper](https://doi.org/10.1016/j.isprsjprs.2024.10.026) |
| **LRTCP** — Low-Rank Tensor Completion Pansharpening Based on Haze Correction | TGRS | M | Weather | [Paper](https://doi.org/10.1109/TGRS.2024.3405848) |
| **MRFS** — MRFS: Mutually Reinforcing Image Fusion and Segmentation | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2024/papers/Zhang_MRFS_Mutually_Reinforcing_Image_Fusion_and_Segmentation_CVPR_2024_paper.pdf) |
| **Nested hypersharpening** — Spatial Resolution Enhancement of Vegetation Indexes via Fusion of Hyperspectral and Multispectral Satellite Data | Remote Sensing | M | Foundation | [Paper](https://doi.org/10.3390/rs16050875) |
| **SCT-CR** — SCT-CR: A synergistic convolution-transformer modeling method using SAR-optical data fusion for cloud removal | International Journal of Applied Earth Observation and Geoinformation | D | Weather | [Paper](https://doi.org/10.1016/j.jag.2024.103909) |
| **Text-DiFuse** — Text-DiFuse: An Interactive Multi-Modal Image Fusion Framework based on Text-modulated Diffusion Model | NeurIPS | G | Foundation | [Paper](https://papers.nips.cc/paper_files/paper/2024/hash/45e409b46bebd648e9041a628a1a9964-Abstract-Conference.html) · [Source](https://github.com/Leiii-Cao/Text-DiFuse) |
| **Text-IF** — Text-IF: Leveraging Semantic Text Guidance for Degradation-Aware and Interactive Image Fusion | CVPR | D | Foundation | [Paper](https://arxiv.org/abs/2403.16387) · [Source](https://github.com/XunpengYi/Text-IF) |
| **USSRN** — Cloud Removal With SAR-Optical Data Fusion Using a Unified Spatial–Spectral Residual Network | TGRS | D | Weather | [Paper](https://doi.org/10.1109/tgrs.2023.3339210) |
| **VIFNet** — VIFNet: An end-to-end visible–infrared fusion network for image dehazing | Neurocomputing | D | Weather | [Paper](https://doi.org/10.1016/j.neucom.2024.128105) · [Source](https://github.com/mengyu212/VIFNet_dehazing) |
| **VN-Dehaze** — Color-preserving visible and near-infrared image fusion for removing fog | Infrared Physics & Technology | M | Weather | [Paper](https://doi.org/10.1016/j.infrared.2024.105252) |
| **Weather-gated LRF** — Towards Robust 3D Object Detection with LiDAR and 4D Radar Fusion in Various Weather Conditions | CVPR | D | Weather | [Paper](https://openaccess.thecvf.com/content/CVPR2024/html/Chae_Towards_Robust_3D_Object_Detection_with_LiDAR_and_4D_Radar_CVPR_2024_paper.html) |

### 2023

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **Attention GAN CR** — Cloud removal using SAR and optical images via attention mechanism-based GAN | Pattern Recognition Letters | D | Weather | [Paper](https://doi.org/10.1016/j.patrec.2023.09.014) |
| **CDDFuse** — CDDFuse: Correlation-Driven Dual-Branch Feature Decomposition for Multi-Modality Image Fusion | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2023/html/Zhao_CDDFuse_Correlation-Driven_Dual-Branch_Feature_Decomposition_for_Multi-Modality_Image_Fusion_CVPR_2023_paper.html) · [Source](https://github.com/Zhaozixiang1228/MMIF-CDDFuse) |
| **DATFuse** — DATFuse: Infrared and Visible Image Fusion via Dual Attention Transformer | TCSVT | D | Foundation | [Paper](https://doi.org/10.1109/TCSVT.2023.3234340) |
| **DDFM** — DDFM: Denoising Diffusion Model for Multi-Modality Image Fusion | ICCV | G | Foundation | [Paper](https://openaccess.thecvf.com/content/ICCV2023/html/Zhao_DDFM_Denoising_Diffusion_Model_for_Multi-Modality_Image_Fusion_ICCV_2023_paper.html) · [Source](https://github.com/Zhaozixiang1228/MMIF-DDFM) |
| **DDPM-Fus** — Hyperspectral and Multispectral Image Fusion Using the Conditional Denoising Diffusion Probabilistic Model | arXiv preprint | G | Foundation | [Paper](https://doi.org/10.48550/arXiv.2307.03423) |
| **Dif-Fusion** — Dif-Fusion: Toward High Color Fidelity in Infrared and Visible Image Fusion With Diffusion Models | TIP | D | Foundation | [Paper](https://doi.org/10.1109/TIP.2023.3322046) |
| **DIVFusion** — DIVFusion: Darkness-free infrared and visible image fusion | Information Fusion | D | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2022.10.034) |
| **Edge-SAR** — Edge-SAR-Assisted Multimodal Fusion for Enhanced Cloud Removal | GRSL | D | Weather | [Paper](https://doi.org/10.1109/lgrs.2023.3307240) |
| **HS2P** — HS2P: Hierarchical spectral and structure-preserving fusion network for multimodal remote sensing image cloud and shadow removal | Information Fusion | D | Weather | [Paper](https://doi.org/10.1016/j.inffus.2023.02.002) |
| **LRRNet** — LRRNet: A Novel Representation Learning Guided Fusion Framework for Infrared and Visible Images | TPAMI | M | Foundation | [Paper](https://doi.org/10.1109/TPAMI.2023.3268209) |
| **MetaBEV** — MetaBEV: Solving Sensor Failures for 3D Detection and Map Segmentation | ICCV | D | Foundation | [Paper](https://doi.org/10.1109/iccv51070.2023.00801) |
| **MetaFusion** — MetaFusion: Infrared and Visible Image Fusion via Meta-Feature Embedding From Object Detection | CVPR | D | Foundation | [Paper](https://doi.org/10.1109/CVPR52729.2023.01341) · [Source](https://github.com/wdzhao123/MetaFusion) |
| **MT-DETR** — MT-DETR: Robust End-to-end Multimodal Detection with Confidence Fusion | 2023 IEEE/CVF Winter Conference on Applications of Computer Vision (WACV) | D | Weather | [Paper](https://doi.org/10.1109/wacv56688.2023.00522) |
| **PAIF** — PAIF: Perception-Aware Infrared-Visible Image Fusion for Attack-Tolerant Semantic Segmentation | Proceedings of the 31st ACM International Conference on Multimedia | D | Foundation | [Paper](https://doi.org/10.1145/3581783.3611928) |
| **PSFusion** — Rethinking the necessity of image fusion in high-level vision tasks: A practical infrared and visible image fusion network based on progressive semantic injection and scene fidelity | Information Fusion | D | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2023.101870) |
| **SegMiF** — Multi-interactive Feature Learning and a Full-time Multi-modality Benchmark for Image Fusion and Segmentation | ICCV | D | Foundation | [Paper](https://openaccess.thecvf.com/content/ICCV2023/html/Liu_Multi-interactive_Feature_Learning_and_a_Full-time_Multi-modality_Benchmark_for_Image_ICCV_2023_paper.html) · [Source](https://github.com/JinyuanLiu-CV/SegMiF) |
| **UnCRtainTS** — UnCRtainTS: Uncertainty Quantification for Cloud Removal in Optical Satellite Time Series | Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW) | D | Weather | [Paper](https://doi.org/10.1109/CVPRW59228.2023.00202) · [Source](https://github.com/PatrickTUM/UnCRtainTS) |

### 2022

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **AUIF** — Efficient and Model-Based Infrared and Visible Image Fusion via Algorithm Unrolling | TCSVT | M | Foundation | [Paper](https://doi.org/10.1109/TCSVT.2021.3075745) |
| **DeFusion** — Fusion from Decomposition: A Self-Supervised Decomposition Approach for Image Fusion | ECCV | D | Foundation | [Paper](https://doi.org/10.1007/978-3-031-19797-0_41) |
| **DIP-HyperKite** — Hyperspectral Pansharpening Based on Improved Deep Image Prior and Residual Reconstruction | TGRS | D | Foundation | [Paper](https://doi.org/10.1109/tgrs.2021.3139292) · [Source](https://github.com/wgcban/DIP-HyperKite) |
| **GLF-CR** — GLF-CR: SAR-enhanced cloud removal with global–local fusion | ISPRS Journal of Photogrammetry and Remote Sensing | D | Weather | [Paper](https://doi.org/10.1016/j.isprsjprs.2022.08.002) · [Source](https://github.com/xufangchn/GLF-CR) |
| **HydraFusion** — HydraFusion: Context-Aware Selective Sensor Fusion for Robust and Efficient Autonomous Vehicle Perception | 2022 ACM/IEEE 13th International Conference on Cyber-Physical Systems (ICCPS) | D | Weather | [Paper](https://doi.org/10.1109/iccps54341.2022.00013) |
| **PIAFusion** — PIAFusion: A progressive infrared and visible image fusion network based on illumination aware | Information Fusion | D | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2022.03.007) |
| **SeAFusion** — Image fusion in the loop of high-level vision tasks: A semantic-aware real-time infrared and visible image fusion network | Information Fusion | D | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2021.12.004) · [Source](https://github.com/Linfeng-Tang/SeAFusion) |
| **ST-MVDNet** — Modality-Agnostic Learning for Radar-Lidar Fusion in Vehicle Detection | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Li_Modality-Agnostic_Learning_for_Radar-Lidar_Fusion_in_Vehicle_Detection_CVPR_2022_paper.html) |
| **SwinFusion** — SwinFusion: Cross-domain Long-range Learning for General Image Fusion via Swin Transformer | IEEE/CAA Journal of Automatica Sinica | D | Foundation | [Paper](https://doi.org/10.1109/JAS.2022.105686) · [Source](https://github.com/Linfeng-Tang/SwinFusion) |
| **TarDAL** — Target-Aware Dual Adversarial Learning and a Multi-Scenario Multi-Modality Benchmark To Fuse Infrared and Visible for Object Detection | CVPR | D | Foundation | [Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Liu_Target-Aware_Dual_Adversarial_Learning_and_a_Multi-Scenario_Multi-Modality_Benchmark_To_CVPR_2022_paper.html) · [Source](https://github.com/JinyuanLiu-CV/TarDAL) |
| **Two-flow CR** — Cloud Removal Based on SAR-Optical Remote Sensing Data Fusion via a Two-Flow Network | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | D | Weather | [Paper](https://doi.org/10.1109/jstars.2022.3203508) |
| **U2Fusion** — U2Fusion: A Unified Unsupervised Image Fusion Network | TPAMI | D | Foundation | [Paper](https://doi.org/10.1109/TPAMI.2020.3012548) · [Source](https://github.com/hanna-xu/U2Fusion) |
| **UMF-CMGR** — Unsupervised Misaligned Infrared and Visible Image Fusion via Cross-Modality Image Generation and Registration | Proceedings of the International Joint Conference on Artificial Intelligence (IJCAI) | D | Foundation | [Paper](https://doi.org/10.24963/ijcai.2022/487) |

### 2021

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **All-season CR** — Multisensor Data Fusion for Cloud Removal in Global and All-Season Sentinel-2 Imagery | TGRS | D | Weather | [Paper](https://doi.org/10.1109/TGRS.2020.3024744) |
| **CU-Net** — Deep Convolutional Neural Network for Multi-Modal Image Restoration and Fusion | TPAMI | M | Foundation | [Paper](https://doi.org/10.1109/TPAMI.2020.2984244) |
| **MVDNet** — Robust Multimodal Vehicle Detection in Foggy Weather Using Complementary Lidar and Radar Signals | CVPR | D | Weather | [Paper](https://openaccess.thecvf.com/content/CVPR2021/html/Qian_Robust_Multimodal_Vehicle_Detection_in_Foggy_Weather_Using_Complementary_Lidar_CVPR_2021_paper.html) |
| **RFN-Nest** — RFN-Nest: An end-to-end residual fusion network for infrared and visible images | Information Fusion | D | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2021.02.023) |
| **SDNet** — SDNet: A Versatile Squeeze-and-Decomposition Network for Real-Time Image Fusion | IJCV | D | Foundation | [Paper](https://doi.org/10.1007/s11263-021-01501-8) |
| **STDFusionNet** — STDFusionNet: An Infrared and Visible Image Fusion Network Based on Salient Target Detection | IEEE Transactions on Instrumentation and Measurement | D | Foundation | [Paper](https://doi.org/10.1109/TIM.2021.3075747) · [Source](https://github.com/Linfeng-Tang/STDFusionNet) |

### 2020

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **CMD** — Thick Cloud Removal With Optical and SAR Imagery via Convolutional-Mapping-Deconvolutional Network | TGRS | D | Weather | [Paper](https://doi.org/10.1109/tgrs.2019.2956959) |
| **DDcGAN** — DDcGAN: A Dual-Discriminator Conditional Generative Adversarial Network for Multi-Resolution Image Fusion | TIP | D | Foundation | [Paper](https://doi.org/10.1109/TIP.2020.2977573) |
| **DIDFuse** — DIDFuse: Deep Image Decomposition for Infrared and Visible Image Fusion | Proceedings of the International Joint Conference on Artificial Intelligence (IJCAI) | D | Foundation | [Paper](https://doi.org/10.24963/ijcai.2020/135) |
| **DSen2-CR** — Cloud removal in Sentinel-2 imagery using a deep residual neural network and SAR-optical data fusion | ISPRS Journal of Photogrammetry and Remote Sensing | D | Weather | [Paper](https://doi.org/10.1016/j.isprsjprs.2020.05.013) · [Source](https://github.com/ameraner/dsen2-cr) |
| **FusionDN** — FusionDN: A Unified Densely Connected Network for Image Fusion | AAAI | D | Foundation | [Paper](https://doi.org/10.1609/aaai.v34i07.6936) |
| **IFCNN** — IFCNN: A general image fusion framework based on convolutional neural network | Information Fusion | D | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2019.07.011) |
| **MDLatLRR** — MDLatLRR: A Novel Decomposition Method for Infrared and Visible Image Fusion | TIP | M | Foundation | [Paper](https://doi.org/10.1109/TIP.2020.2975984) |
| **NestFuse** — NestFuse: An Infrared and Visible Image Fusion Architecture Based on Nest Connection and Spatial/Channel Attention Models | IEEE Transactions on Instrumentation and Measurement | D | Foundation | [Paper](https://doi.org/10.1109/TIM.2020.3005230) |
| **PMGI** — Rethinking the Image Fusion: A Fast Unified Image Fusion Network based on Proportional Maintenance of Gradient and Intensity | AAAI | D | Foundation | [Paper](https://doi.org/10.1609/aaai.v34i07.6975) |
| **Seeing Through Fog** — Seeing Through Fog Without Seeing Fog: Deep Multimodal Sensor Fusion in Unseen Adverse Weather | CVPR | D | Weather | [Paper](https://openaccess.thecvf.com/content_CVPR_2020/html/Bijelic_Seeing_Through_Fog_Without_Seeing_Fog_Deep_Multimodal_Sensor_Fusion_CVPR_2020_paper.html) |
| **Simulation-fusion** — Cloud Removal with Fusion of High Resolution Optical and SAR Images Using Generative Adversarial Networks | Remote Sensing | D | Weather | [Paper](https://doi.org/10.3390/rs12010191) |

### 2019

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **Cloud-aware pan** — Pansharpening for Cloud-Contaminated Very High-Resolution Remote Sensing Images | TGRS | M | Weather | [Paper](https://doi.org/10.1109/TGRS.2018.2878007) |
| **DenseFuse** — DenseFuse: A Fusion Approach to Infrared and Visible Images | TIP | D | Foundation | [Paper](https://doi.org/10.1109/TIP.2018.2887342) · [Source](https://github.com/hli1221/imagefusion_densefuse) |
| **FusionGAN** — FusionGAN: A generative adversarial network for infrared and visible image fusion | Information Fusion | D | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2018.09.004) |

### 2018

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **NIR dehazing** — Near-Infrared Fusion for Photorealistic Image Dehazing | Proceedings of the IS&T International Symposium on Electronic Imaging: Color Imaging XXIII | M | Weather | [Paper](https://doi.org/10.2352/ISSN.2470-1173.2018.16.COLOR-321) · [Source](https://github.com/IVRL/NIRdehazing) |
| **SAR-Opt-cGAN** — A Conditional Generative Adversarial Network to Fuse SAR and Multispectral Optical Data for Cloud Removal from Sentinel-2 Images | Proceedings of the IEEE International Geoscience and Remote Sensing Symposium (IGARSS) | D | Weather | [Paper](https://doi.org/10.1109/IGARSS.2018.8519215) |

### 2017

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **Haze-corrected HPM** — Haze Correction for Contrast-Based Multispectral Pansharpening | GRSL | M | Weather | [Paper](https://doi.org/10.1109/LGRS.2017.2761021) |
| **Improved haze-ratio fusion** — Improvement of a Pansharpening Method Taking Into Account Haze | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | M | Weather | [Paper](https://doi.org/10.1109/jstars.2017.2730221) |
| **PanNet** — PanNet: A Deep Network Architecture for Pan-Sharpening | ICCV | D | Foundation | [Paper](https://doi.org/10.1109/iccv.2017.193) · [Source](https://github.com/liangjiandeng/DLPan-Toolbox) |
| **RGB-NIR transfer** — Colour image dehazing using near-infrared fusion | IET Image Processing | M | Weather | [Paper](https://doi.org/10.1049/iet-ipr.2017.0192) |

### 2016

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **GTF** — Infrared and visible image fusion via gradient transfer and total variation minimization | Information Fusion | M | Foundation | [Paper](https://doi.org/10.1016/j.inffus.2016.02.001) · [Source](https://github.com/jiayi-ma/GTF) |
| **PNN** — Pansharpening by Convolutional Neural Networks | Remote Sensing | D | Foundation | [Paper](https://doi.org/10.3390/rs8070594) · [Source](https://github.com/liangjiandeng/DLPan-Toolbox) |

### 2015

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **FUSE** — Fast Fusion of Multi-Band Images Based on Solving a Sylvester Equation | TIP | M | Foundation | [Paper](https://doi.org/10.1109/tip.2015.2458572) |
| **HySure** — A Convex Formulation for Hyperspectral Image Superresolution via Subspace-Based Regularization | TGRS | M | Foundation | [Paper](https://doi.org/10.1109/tgrs.2014.2375320) |
| **Sparse SAR-optical CR** — Cloud Removal From Optical Satellite Imagery With SAR Imagery Using Sparse Representation | GRSL | M | Weather | [Paper](https://doi.org/10.1109/lgrs.2014.2377476) |

### 2013

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **GFF** — Image Fusion With Guided Filtering | TIP | M | Foundation | [Paper](https://doi.org/10.1109/TIP.2013.2244222) · [Source](https://github.com/jiayi-ma/GTF) |

### 2012

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **CNMF** — Coupled Nonnegative Matrix Factorization Unmixing for Hyperspectral and Multispectral Data Fusion | TGRS | M | Foundation | [Paper](https://doi.org/10.1109/tgrs.2011.2161320) |

### 2009

| Paper / method | Venue | Family | Scope | Resources |
| :-- | :-- | :-- | :-- | :-- |
| **Schaul et al** — Color image dehazing using the near-infrared | ICIP | M | Weather | [Paper](https://doi.org/10.1109/ICIP.2009.5413700) |

## Datasets and benchmarks

The [full dataset inventory](docs/datasets.md) records 51 resources with modalities, weather origin, original counting units, reference types, alignment, access routes, and qualifications. Downloadable data do not automatically provide pixel-aligned pairs, a clean target, or a reusable data license.

| Research setting | Representative resources | What to check |
| :-- | :-- | :-- |
| Controlled VIS–thermal weather fusion | AWMM-100K, DeMMI-RF, SWVI, FOGIV | Parent-scene overlap; synthetic weather generation; pre-corruption source references. |
| Real VIS–thermal fusion and semantics | FMB; M3FD and other conventional controls | Actual weather labels; registration; semantic labels; no unique ideal fused image. |
| SAR–optical cloud reconstruction | SEN12MS-CR, SEN12MS-CR-TS, AllClear, M3R-CR | Acquisition dates; available temporal observations; cloud/shadow masks; geographic independence. |
| PAN–MS thin-cloud fusion | Pan-TCR-GF2 | Spectral response; scale ratio; real thin-cloud coverage; reduced/full-resolution protocols. |
| Hyperspectral and cross-resolution fusion | Houston 2013, Houston 2018, Chikusei and spatial–spectral controls | Cloud shadow versus paired restoration; spectral calibration; real resolution mismatch. |
| Camera/range/event perception | MUSES, Seeing Through Fog, DeLiVER, RADIATE, CADC, MS2 | Exact sensor subset; synchronization; modality failures; task annotations; real versus simulated weather. |

Selection should follow the research question. Covering distinct weather, sensor, reference, and downstream-label requirements is more informative than ranking heterogeneous datasets with one arbitrary quality score. Related releases and synthetic derivatives should not be treated as independent scenes.

## Research directions

- **Evidence-preserving multimodal foundation models.** Use broad visual priors while preserving sensor-supported structure, spectra, and thermal evidence; evaluate hallucination and cross-modal contradictions.
- **Conditioning that survives unseen weather.** Learn reliable, local estimates of degradation and sensor usefulness; report prompt sensitivity and the information available at test time.
- **Joint sensor failure and imperfect alignment.** Test missing observations, calibration drift, asynchronous capture, and weather that simultaneously degrades multiple modalities.
- **Real-weather and cross-domain evaluation.** Separate synthetic performance from real acquisition, and split by scene, geography, sequence, and parent dataset.
- **Quality beyond appearance.** Combine source-information preservation, artifact detection, physical fidelity, and task utility under clearly specified output contracts.
- **Efficient, inspectable deployment.** Account for all encoders, priors, samplers, preprocessing, and external services in latency and memory; compare compute-matched alternatives.

These are research questions rather than claims that larger models automatically improve fusion. Relevant foundations include language-conditioned fusion, diffusion-based fusion, reliability-aware sensing, and task-driven multimodal representation learning in the reading list.

## Contributing

Corrections and additions are welcome through [issues](https://github.com/chdwyb/Adverse-Weather-Image-Fusion-Survey/issues) or pull requests. Please provide:

1. The exact paper title, authors, venue/year, and a primary publication or preprint link.
2. The observed modalities, weather setting, output domain, and primary fusion mechanism.
3. An author-linked repository, if available, distinguishing complete implementations, inference-only releases, SDKs, and placeholders.
4. For datasets, original sample units, splits, reference types, access conditions, and parent-dataset relationships.

Keep preprints distinct from formal publications and avoid duplicate entries for the same study. [CONTRIBUTING.md](CONTRIBUTING.md) gives the record format.

## Acknowledgements

The resource-oriented organization was inspired by the [All-in-One Image Restoration Survey repository](https://github.com/Harbinzzy/All-in-One-Image-Restoration-Survey). The descriptions and organization here are tailored to multimodal fusion. Credit for every linked paper, implementation, and dataset belongs to its authors and maintainers; their respective licenses and access terms apply.
