# Methods by fusion mechanism

[Home](../README.md) · [Chronological papers](../README.md#papers-by-year) · [Public implementations](implementations.md)

Primary families describe the estimation mechanism. Conditioning, semantic/task supervision, physical priors, and restoration coupling are orthogonal attributes. A supporting foundation is not automatically a weather-specialist method.

In compact modality notation, V is visible, T thermal infrared, N near-infrared, I infrared with unresolved band, P panchromatic, M multispectral, H hyperspectral, S SAR, L LiDAR, R radar, and E events. Weather codes R/H/S/C denote rain/haze or fog/snow/cloud. Their context separates sensor and weather notation. FI means a fused display image, HR high resolution, and NR not resolved from inspected primary sources.

## Model-derived inference

### AWFusion (2026)

**All-weather Multi-Modality Image Fusion: Unified Framework and 100k Benchmark** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2026.104130). Scope: weather-related.

**Observations and conditions:** V, T; R, H, S.

**Mechanism and boundary:** Learned low-rank decomposition and sparse feature fusion explicitly unroll convolutional sparse-coding updates; physical clear-feature equations constrain recovery.

**Additional attributes:** unrolled sparse coding; physical prior; distillation; restoration coupling.

**Implementation:** [Public source](https://github.com/ixilai/AWFusion); public source link; configuration and dependencies must be checked.

### FIVFusion (2025)

**FIVFusion: Fog-free infrared and visible image fusion** — Journal of King Saud University Computer and Information Sciences. [Paper](https://doi.org/10.1007/s44443-025-00309-7). Scope: weather-related.

**Observations and conditions:** TIR + foggy VIS; Fog; synthetic FOGIV scattering data.

**Mechanism and boundary:** Visible physical-aware block derives feature recovery from scattering-model inversion (Eqs.3-7); learned parameters remain inside that model-derived inference block.

**Additional attributes:** physical feature inversion; learned perception weights; restoration coupling.

**Implementation:** [Public source](https://github.com/XiangheBi/FIVFusion); public source link; configuration and dependencies must be checked.

### FoggyFuse (2025)

**FoggyFuse: Infrared and visible image fusion method based on saturation line prior in foggy conditions** — Optics & Laser Technology. [Paper](https://doi.org/10.1016/j.optlastec.2025.113075). Scope: weather-related.

**Observations and conditions:** IR + VIS affected by fog; exact infrared spectral band not independently verified; Fog; smoke is discussed as a target scenario.

**Mechanism and boundary:** Saturation-line transmission prior and weighted guided filtering, followed by auxiliary enhancement and NSST edge-enhanced fusion. Output: Fused image. Constraint: Analytic/model-based; no learned training supervision identified. Physical fog prior is explicit; paper discusses degraded IR as well as VIS. No claim of universal all-weather validity.

### LRTCP (2024)

**Low-Rank Tensor Completion Pansharpening Based on Haze Correction** — TGRS. [Paper](https://doi.org/10.1109/TGRS.2024.3405848). Scope: weather-related.

**Observations and conditions:** P, M; H.

**Mechanism and boundary:** Haze lines; low-rank completion. Output: Components / HR-MS. Constraint: Model-based constraints.

### Nested hypersharpening (2024)

**Spatial Resolution Enhancement of Vegetation Indexes via Fusion of Hyperspectral and Multispectral Satellite Data** — Remote Sensing. [Paper](https://doi.org/10.3390/rs16050875). Scope: supporting foundation.

**Observations and conditions:** EnMAP HS + Sentinel-2 MS; atmospheric correction assumed; not adverse-weather benchmark.

**Mechanism and boundary:** Nested physical hypersharpening with spectral consistency evaluation. Output: 10 m hyperspectral product and vegetation indices. Constraint: Model-based estimation from observations; no paired neural-network training. Haze term in formulation does not establish an adverse-weather experiment; actual Level-2 surface reflectance data and favorable conditions.

### VN-Dehaze (2024)

**Color-preserving visible and near-infrared image fusion for removing fog** — Infrared Physics & Technology. [Paper](https://doi.org/10.1016/j.infrared.2024.105252). Scope: weather-related.

**Observations and conditions:** V, N; H.

**Mechanism and boundary:** Spectral complementation for dehazing. Output: RGB. Constraint: NR.

### LRRNet (2023)

**LRRNet: A Novel Representation Learning Guided Fusion Framework for Infrared and Visible Images** — TPAMI. [Paper](https://doi.org/10.1109/TPAMI.2023.3268209). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Low-rank representation optimization converted into a feed-forward learned fusion architecture. Output: Fused image. Constraint: Source detail-to-semantic constraints; no ideal fused target reported. Model-derived network rather than an unconstrained architecture; weather-specific degradation identification is not verified.

### AUIF (2022)

**Efficient and Model-Based Infrared and Visible Image Fusion via Algorithm Unrolling** — TCSVT. [Paper](https://doi.org/10.1109/TCSVT.2021.3075745). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Two-scale optimization iterations are unrolled into learned base/detail decomposers and a reconstructor. Output: Fused image. Constraint: Self reconstruction during training; fusion rule at inference. Final issue 2022; online 2021 and arXiv 2020. Count one method record.

### CU-Net (2021)

**Deep Convolutional Neural Network for Multi-Modal Image Restoration and Fusion** — TPAMI. [Paper](https://doi.org/10.1109/TPAMI.2020.2984244). Scope: supporting foundation.

**Observations and conditions:** RGB-depth; flash/non-flash; multifocus/multiexposure; RGB-MS examples in code; Noise, resolution/photographic degradation; not weather-specialist.

**Mechanism and boundary:** Network modules derive from multimodal convolutional sparse coding, separating common and modality-unique information. Output: Restored target or fused image, depending on task. Constraint: Task-dependent restoration/fusion training; no single supervision label for all applications. Provides the conceptual boundary between guidance-only restoration and information-combining fusion. Not an IR-VIS weather benchmark method.

### MDLatLRR (2020)

**MDLatLRR: A Novel Decomposition Method for Infrared and Visible Image Fusion** — TIP. [Paper](https://doi.org/10.1109/TIP.2020.2975984). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Multilevel latent low-rank decomposition; nuclear-norm detail weighting and base averaging. Output: Fused image. Constraint: Analytic decomposition with learned projection; no ideal fused targets. Low-rank/salient decomposition is a structural prior, not an explicit atmospheric observation model.

### Cloud-aware pan (2019)

**Pansharpening for Cloud-Contaminated Very High-Resolution Remote Sensing Images** — TGRS. [Paper](https://doi.org/10.1109/TGRS.2018.2878007). Scope: weather-related.

**Observations and conditions:** P, M^t; C, H.

**Mechanism and boundary:** Temporal/spatial variational fusion. Output: Components / HR-MS. Constraint: Variational prior; NR.

### NIR dehazing (2018)

**Near-Infrared Fusion for Photorealistic Image Dehazing** — Proceedings of the IS&T International Symposium on Electronic Imaging: Color Imaging XXIII. [Paper](https://doi.org/10.2352/ISSN.2470-1173.2018.16.COLOR-321). Scope: weather-related.

**Observations and conditions:** V, N; H.

**Mechanism and boundary:** Multiscale spectral consistency. Output: Components / RGB. Constraint: Handcrafted prior.

**Implementation:** [Public source](https://github.com/IVRL/NIRdehazing); public source link; configuration and dependencies must be checked.

### Haze-corrected HPM (2017)

**Haze Correction for Contrast-Based Multispectral Pansharpening** — GRSL. [Paper](https://doi.org/10.1109/LGRS.2017.2761021). Scope: weather-related.

**Observations and conditions:** P, M; H.

**Mechanism and boundary:** Path-radiance-aware detail injection. Output: Image / HR-MS. Constraint: Physical injection rule.

### Improved haze-ratio fusion (2017)

**Improvement of a Pansharpening Method Taking Into Account Haze** — IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing. [Paper](https://doi.org/10.1109/jstars.2017.2730221). Scope: weather-related.

**Observations and conditions:** PAN + MS; haze compensation.

**Mechanism and boundary:** Haze estimates and ratio-based spatial detail transfer. Output: high-resolution MS. Constraint: Model-based estimation from observations; no paired neural-network training.

### RGB-NIR transfer (2017)

**Colour image dehazing using near-infrared fusion** — IET Image Processing. [Paper](https://doi.org/10.1049/iet-ipr.2017.0192). Scope: weather-related.

**Observations and conditions:** V, N; H.

**Mechanism and boundary:** Visible base correction; NIR detail transfer. Output: RGB. Constraint: Analytic prior.

### GTF (2016)

**Infrared and visible image fusion via gradient transfer and total variation minimization** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2016.02.001). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS, including unregistered extension; No explicit weather model; misregistration extension.

**Mechanism and boundary:** L1-TV objective preserves IR intensity and transfers VIS gradient structure. Output: Fused image. Constraint: Analytic variational optimization. Transfers gradients from VIS, so corruption sensitivity is an experimental question rather than an assumed property.

**Implementation:** [Public source](https://github.com/jiayi-ma/GTF); analytical MATLAB implementation; no trained weights required.

### FUSE (2015)

**Fast Fusion of Multi-Band Images Based on Solving a Sylvester Equation** — TIP. [Paper](https://doi.org/10.1109/tip.2015.2458572). Scope: supporting foundation.

**Observations and conditions:** low-resolution HS + high-resolution MS/PAN; none; clear-scene foundation.

**Mechanism and boundary:** Fast Sylvester-equation solution of observation-model fusion. Output: high-resolution HS. Constraint: Model-based estimation from observations; no paired neural-network training.

### HySure (2015)

**A Convex Formulation for Hyperspectral Image Superresolution via Subspace-Based Regularization** — TGRS. [Paper](https://doi.org/10.1109/tgrs.2014.2375320). Scope: supporting foundation.

**Observations and conditions:** low-resolution HS + high-resolution MS/PAN; none; clear-scene foundation.

**Mechanism and boundary:** Subspace representation with vector total-variation regularization. Output: high-resolution HS. Constraint: Model-based estimation from observations; no paired neural-network training.

### Sparse SAR-optical CR (2015)

**Cloud Removal From Optical Satellite Imagery With SAR Imagery Using Sparse Representation** — GRSL. [Paper](https://doi.org/10.1109/lgrs.2014.2377476). Scope: weather-related.

**Observations and conditions:** cloudy high-resolution optical + low-resolution optical composite (MODIS) + SAR; cloud occlusion.

**Mechanism and boundary:** Coupled optical/optical and optical/SAR gradient dictionaries transfer low- and high-frequency structure. Output: reconstructed high-resolution optical. Constraint: Paired cloud-free patches for coupled dictionary learning. Requires low-resolution optical composite in addition to SAR; not a two-input cloudy-optical/SAR baseline.

### GFF (2013)

**Image Fusion With Guided Filtering** — TIP. [Paper](https://doi.org/10.1109/TIP.2013.2244222). Scope: supporting foundation.

**Observations and conditions:** Multimodal images including IR + VIS; No explicit weather model.

**Mechanism and boundary:** Two-scale base/detail decomposition and guided-filter weight maps enforcing spatial consistency. Output: Fused image. Constraint: No neural-network training. Established deterministic baseline; no weather-specific observation model. Primary text is author-uploaded accepted paper.

**Implementation:** [Public source](https://github.com/jiayi-ma/GTF); analytical MATLAB implementation; no trained weights required.

### CNMF (2012)

**Coupled Nonnegative Matrix Factorization Unmixing for Hyperspectral and Multispectral Data Fusion** — TGRS. [Paper](https://doi.org/10.1109/tgrs.2011.2161320). Scope: supporting foundation.

**Observations and conditions:** low-resolution HS + high-resolution MS; none; clear-scene foundation.

**Mechanism and boundary:** Coupled spectral unmixing with shared endmembers/abundances. Output: high-resolution HS. Constraint: Model-based estimation from observations; no paired neural-network training.

### Schaul et al (2009)

**Color image dehazing using the near-infrared** — ICIP. [Paper](https://doi.org/10.1109/ICIP.2009.5413700). Scope: weather-related.

**Observations and conditions:** V, N; H.

**Mechanism and boundary:** Multiscale spectral information transfer. Output: Components / RGB. Constraint: Handcrafted prior.

## Direct learned estimation

### AMG-Fuse (2026)

**Multi-modality Image Fusion Under Adverse Weather: Mask-Guided Feature Restoration and Interaction** — ECCV. [Paper](https://doi.org/10.1007/978-3-032-37602-2_7). Scope: weather-related.

**Observations and conditions:** V, T; R, H, S.

**Mechanism and boundary:** Contribution masks; cross-attention. Output: Features / FI. Constraint: EMMA pseudo-targets; masks.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

**Implementation:** [Public source](https://github.com/ixilai/AMG-Fuse); public source link; configuration and dependencies must be checked.

### AWM-Fuse (2026)

**AWM-Fuse: Multi-Modality Image Fusion for Adverse Weather via Global and Local Text Perception** — TIP. [Paper](https://doi.org/10.1109/TIP.2026.3690324). Scope: weather-related.

**Observations and conditions:** V, T; W.

**Mechanism and boundary:** Global/local text-conditioned fusion. Output: Features / FI. Constraint: Target construction NR.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

**Implementation:** [Public source](https://github.com/Feecuin/AWM-Fuse); public source link; configuration and dependencies must be checked.

### CAWM-Mamba (2026)

**CAWM-Mamba: A unified model for infrared-visible image fusion and compound adverse weather restoration** — Expert Systems with Applications. [Paper](https://doi.org/10.1016/j.eswa.2026.131665). Scope: weather-related.

**Observations and conditions:** V, T; R, H, S, mix.

**Mechanism and boundary:** Weather-conditioned wavelet SSM. Output: Features / FI. Constraint: Target construction NR.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

**Implementation:** [Public source](https://github.com/Feecuin/CAWM-Mamba); public source link; configuration and dependencies must be checked.

### DACDM-CR (2026)

**DACDM-CR: Discriminative attention and cloud-aware dynamic mamba for SAR-assisted optical data cloud removal** — Digital Signal Processing. [Paper](https://doi.org/10.1016/j.dsp.2025.105522). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Discriminative interaction plus cloud-adaptive gated state-space reconstruction. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

### DGFusion (2026)

**DGFusion: Depth-Guided Sensor Fusion for Robust Semantic Perception** — IEEE Robotics and Automation Letters. [Paper](https://doi.org/10.1109/lra.2026.3656789). Scope: weather-related.

**Observations and conditions:** MUSES: RGB + LiDAR + radar + events; DeLiVER: RGB + LiDAR + depth + events; MUSES and DeLiVER adverse conditions.

**Mechanism and boundary:** Local depth tokens plus global condition token for spatially varying fusion. Output: semantic/panoptic segmentation. Constraint: Semantic/panoptic labels; paper-specific condition supervision and auxiliary depth learning. Repository explicitly omits training code; inference/weights only, not a full retraining implementation.

**Additional attributes:** explicit conditioning; see source for training/inference scope; task guidance.

**Implementation:** [Public source](https://github.com/timbroed/DGFusion); public source link; configuration and dependencies must be checked.

### Data-interactive Mamba (2026)

**Data-interactive mamba driven SAR-optical fusion cloud removal** — Knowledge-Based Systems. [Paper](https://doi.org/10.1016/j.knosys.2026.115301). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud and shadow.

**Mechanism and boundary:** Data-interactive vision Mamba with adaptive cloud-shadow loss. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

**Additional attributes:** explicit conditioning; see source for training/inference scope; cloud-dependent training objective.

### Doppler-guided cooperative fusion (2026)

**4-D Radar Meets LiDAR and Camera: Cooperative Perception under Adverse Weather** — Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops. [Paper](https://openaccess.thecvf.com/content/CVPR2026W/DriveX/html/Yazgan_4-D_Radar_Meets_LiDAR_and_Camera_Cooperative_Perception_under_Adverse_CVPRW_2026_paper.html). Scope: weather-related.

**Observations and conditions:** Cooperative camera + radar OR LiDAR + radar configurations; simulated fog/rain on OPV2V-R/Adver-City-R; MAN TruckScenes transfer.

**Mechanism and boundary:** Doppler-guided spatial attention for cooperative fusion. Output: detections. Constraint: Detection labels. CVPR2026 DriveX Workshop. Radar-camera and LiDAR-radar variants have distinct input budgets. Key follows project URL; it does not imply SlimComm is the new paper-specific method name.

**Additional attributes:** task guidance.

### HRCP (2026)

**Hybrid Robust Collaborative Perception with LiDAR-4D Radar Fusion under Adverse Weather Conditions** — Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. [Paper](https://openaccess.thecvf.com/content/CVPR2026/papers/Yang_Hybrid_Robust_Collaborative_Perception_with_LiDAR-4D_Radar_Fusion_under_Adverse_CVPR_2026_paper.pdf). Scope: weather-related.

**Observations and conditions:** multi-agent LiDAR + 4D radar; simulated adverse weather in V2X-R; corrupted real V2X-Radar-C evaluation.

**Mechanism and boundary:** Hybrid collaboration, bidirectional cross-modal reliability gating and adaptive feature enhancement. Output: 3D detections. Constraint: 3D detection labels.

**Additional attributes:** task guidance.

### IASSF (2026)

**Infrared-assisted single-stage framework for joint restoration and fusion of visible and infrared images under hazy conditions** — Pattern Recognition. [Paper](https://doi.org/10.1016/j.patcog.2026.113074). Scope: weather-related.

**Observations and conditions:** V, T; H.

**Mechanism and boundary:** TIR-guided features; haze prompts. Output: Features / FI. Constraint: Clean V auxiliary; sources.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

**Implementation:** [Public source](https://github.com/fangjiaqi0909/IASSF); public source link; configuration and dependencies must be checked.

### Mamba-SCR (2026)

**Mamba-SCR: a frequency-domain enhanced state space model for cloud removal with SAR and optical data fusion** — GIScience & Remote Sensing. [Paper](https://doi.org/10.1080/15481603.2026.2677334). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Wavelet gating for SAR speckle and spatial-frequency state-space interaction. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

### MdaIF (2026)

**MdaIF: Robust One-Stop Multi-Degradation-Aware Image Fusion with Language-Driven Semantics** — AAAI. [Paper](https://doi.org/10.1609/aaai.v40i8.37548). Scope: weather-related.

**Observations and conditions:** TIR + degraded VIS; Haze, rain, snow.

**Mechanism and boundary:** VLM semantic priors drive degradation-aware channel attention and mixture-of-experts routing. Output: Fused image. Constraint: NR: abstract verifies VLM priors and MoE, not exact target construction. Three weather types are explicit in the publisher abstract; no claim about compound-weather training is added.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

### NAM-CR (2026)

**NAM-CR: Noise-aware multisensor cloud removal for optical remote sensing imagery by fusing SAR data** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2026.104295). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud; SAR speckle is additional sensor corruption.

**Mechanism and boundary:** Self-attention multimodal aggregation and deep-shallow feature fusion with cloud-guided noise-optimization loss. Output: cloud-free optical/MS. Constraint: Paired optical/cloudy-optical/SAR triplets. Code link redirects to lab site; model source not verified.

**Additional attributes:** cloud-dependent training objective.

### PMNet (2026)

**PMNet: A Positional Mamba Network for SAR-Assisted Cloud Removal** — GRSL. [Paper](https://doi.org/10.1109/lgrs.2026.3726690). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Shared learnable 2-D positional prior before cross-modal Mamba scanning. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

### Pan-TCR (2026)

**Pansharpening for Thin-Cloud Contaminated Remote Sensing Images: A Unified Framework and Benchmark Dataset** — AAAI. [Paper](https://doi.org/10.1609/aaai.v40i5.37369). Scope: weather-related.

**Observations and conditions:** P, M; C_thin.

**Mechanism and boundary:** Frequency analysis motivates NIR-amplitude/PAN-phase prompts in an end-to-end learned FDR/IFC network; these cues do not instantiate a solved or unrolled observation inverse.

**Additional attributes:** physical frequency prior; cross-modal frequency prompts; restoration coupling.

**Implementation:** [Public source](https://github.com/dusongcheng/PanTCR-GF2); training/test source; validation-call repair required.

### VideoFusion (2026)

**VideoFusion: A Spatio-Temporal Collaborative Network for Multi-modal Video Fusion** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2026/html/Tang_VideoFusion_A_Spatio-Temporal_Collaborative_Network_for_Multi-modal_Video_Fusion_CVPR_2026_paper.html). Scope: supporting foundation.

**Observations and conditions:** Temporally aligned TIR + VIS video; Temporal interference; low illumination/overexposure in dataset.

**Mechanism and boundary:** Differential cross-modal reinforcement, complete-modality guidance and bidirectional temporal co-attention. Output: Fused video. Constraint: NR: exact source and temporal training losses not audited. Video temporal consistency is a distinct axis; no rain/fog/snow specialization is inferred from challenging scenes.

### C2RF (2025)

**C2RF: Bridging Multi-modal Image Registration and Fusion via Commonality Mining and Contrastive Learning** — IJCV. [Paper](https://doi.org/10.1007/s11263-025-02427-1). Scope: supporting foundation.

**Observations and conditions:** Misaligned TIR + VIS; also medical pairs; Geometric misalignment, not weather-specific.

**Mechanism and boundary:** Common/unique features support registration; aligned/misaligned fusion results define contrastive registration guidance. Output: Registered/fused image. Constraint: Source/registration constraints and contrastive learning. Registration-fusion coupling addresses geometry; weather corruption would require separate validation.

### CAFuser (2025)

**CAFuser: Condition-Aware Multimodal Fusion for Robust Semantic Perception of Driving Scenes** — IEEE Robotics and Automation Letters. [Paper](https://doi.org/10.1109/lra.2025.3536218). Scope: weather-related.

**Observations and conditions:** MUSES: RGB + LiDAR + radar + events; DeLiVER: RGB + LiDAR + depth + events; real MUSES fog/rain/snow and simulated DeLiVER conditions.

**Mechanism and boundary:** A shared learned backbone, feature adapters and fusion/prediction head directly estimate segmentation; an RGB-derived condition token and semantic supervision are independent attributes.

**Additional attributes:** explicit conditioning; see source for training/inference scope; inference-time conditioning; task guidance; condition token.

**Implementation:** [Public source](https://github.com/timbroed/CAFuser); public source link; configuration and dependencies must be checked.

### CFMW (2025)

**CFMW: Cross-Modality Fusion Mamba for Robust Object Detection Under Adverse Weather** — TCSVT. [Paper](https://doi.org/10.1109/TCSVT.2025.3587918). Scope: weather-related.

**Observations and conditions:** V, T; R, H, S.

**Mechanism and boundary:** Weather handling; state-space fusion. Output: Features / Det. Constraint: Detection; other terms NR.

**Additional attributes:** task guidance.

**Implementation:** [Public source](https://github.com/lhy-zju/CFMW); public source link; configuration and dependencies must be checked.

### ControlFusion (2025)

**ControlFusion: A Controllable Image Fusion Network with Language-Vision Degradation Prompts** — NeurIPS. [Paper](https://doi.org/10.52202/085713-3946). Scope: weather-related.

**Observations and conditions:** V, T; H (modeled), D.

**Mechanism and boundary:** Physical modeling; prompt modulation. Output: Features / FI. Constraint: Target construction NR.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

**Implementation:** [Public source](https://github.com/Linfeng-Tang/ControlFusion); public source link; configuration and dependencies must be checked.

### DAFusion (2025)

**A degradation-aware guided fusion network for infrared and visible image** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2025.102931). Scope: supporting foundation.

**Observations and conditions:** V, T; D.

**Mechanism and boundary:** Author description specifies contrastive degradation representation and co-refinement fusion, not diffusion or adversarial generation.

**Additional attributes:** contrastive degradation representation; source-derived saliency/energy masks.

**Implementation:** [Public source](https://github.com/wang-x-1997/DAFusion); public source link; configuration and dependencies must be checked.

### DLRFusion (2025)

**Doppler-Aware LiDAR-RADAR Fusion for Weather-Robust 3D Detection** — ICCV. [Paper](https://doi.org/10.1109/iccv51701.2025.02525). Scope: weather-related.

**Observations and conditions:** LiDAR + 4D radar power and Doppler; K-Radar normal and adverse weather.

**Mechanism and boundary:** Multi-path iterative LiDAR/power/Doppler interaction. Output: 3D detections. Constraint: Task annotations; no clean fused-image target.

**Additional attributes:** task guidance.

### Dual-domain hierarchical fusion (2025)

**Breaking through clouds: A hierarchical fusion network empowered by dual-domain cross-modality interactive attention for cloud-free image reconstruction** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2024.102649). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** W-shaped dual-stream hierarchy with spatial/frequency cross-modal attention. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

### GIFNet (2025)

**One Model for ALL: Low-Level Task Interaction Is a Key to Task-Agnostic Image Fusion** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2025/papers/Cheng_One_Model_for_ALL_Low-Level_Task_Interaction_Is_a_Key_CVPR_2025_paper.pdf). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; NIR + VIS; medical/photographic/remote tasks; No explicit atmospheric-weather specialization.

**Mechanism and boundary:** Low-level photographic fusion tasks supply pixel-level supervision to task-agnostic multimodal fusion. Output: Fused image. Constraint: Supervised photographic pretext tasks plus unsupervised multimodal task interaction. Primary name is GIFNet, CVPR 2025. Third-party index incorrectly associates its title with later UniFusion/MagicFuse names.

**Additional attributes:** task guidance.

### HaIVFusion (2025)

**HaIVFusion: Haze-Free Infrared and Visible Image Fusion** — IEEE/CAA Journal of Automatica Sinica. [Paper](https://doi.org/10.1109/JAS.2024.124926). Scope: weather-related.

**Observations and conditions:** V, T; H.

**Mechanism and boundary:** Restoration and deep feature fusion. Output: FI. Constraint: NR.

### M3-CR (2025)

**M3-CR: Multiscale Multibranch Mamba for SAR-Assisted Optical Image Thick Cloud Removal** — TGRS. [Paper](https://doi.org/10.1109/tgrs.2025.3566088). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; thick cloud.

**Mechanism and boundary:** Multiscale multibranch state-space fusion. Output: cloud-free optical/MS. Constraint: Not resolved from inspected abstract; retain explicit unknown. Catalogue-level inclusion. Mechanism limited to title; module, supervision and benchmark details require original full-text verification.

### MoME (2025)

**Resilient Sensor Fusion under Adverse Sensor Failures via Multi-Modal Expert Fusion** — CVPR. [Paper](https://doi.org/10.1109/cvpr52734.2025.00630). Scope: weather-related.

**Observations and conditions:** camera + LiDAR; real nuScenes rainy subset; nuScenes-C simulated fog/snow/sunlight; sensor failures.

**Mechanism and boundary:** Three modality experts and adaptive query routing. Output: 3D detections. Constraint: Task annotations; no clean fused-image target.

**Additional attributes:** explicit conditioning; see source for training/inference scope; task guidance.

### PODF-CR (2025)

**Cloud Removal With PolSAR-Optical Data Fusion Using A Two-Flow Residual Network** — arXiv preprint. [Paper](https://doi.org/10.48550/arXiv.2501.07901). Scope: weather-related.

**Observations and conditions:** PolSAR + cloudy optical; cloud occlusion; simulation provenance unresolved from inspected abstract.

**Mechanism and boundary:** PolSAR dynamic-filter denoising, cross-skip optical/PolSAR interaction and attention refinement. Output: cloud-free optical. Constraint: Not resolved from inspected abstract; retain explicit unknown.

### SAG-CR (2025)

**Robust SAR-assisted cloud removal via supervised align-guided fusion and bidirectional hybrid reconstruction** — International Journal of Digital Earth. [Paper](https://doi.org/10.1080/17538947.2025.2472909). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Supervised align-guided fusion and bidirectional hybrid reconstruction. Output: cloud-free optical/MS. Constraint: Supervised alignment guidance and bidirectional hybrid reconstruction.

### SAGE (2025)

**Every SAM Drop Counts: Embracing Semantic Priors for Multi-Modality Image Fusion and Beyond** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2025/html/Wu_Every_SAM_Drop_Counts_Embracing_Semantic_Priors_for_Multi-Modality_Image_CVPR_2025_paper.html). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** SAM semantic priors and persistent attention; bi-level distillation removes SAM dependency at inference. Output: Fused image. Constraint: Pretrained semantic teacher and bi-level distillation; task-adaptability objectives. Semantic prior transfer is verified; improved adverse-weather performance is not assumed.

**Additional attributes:** task guidance.

### SDSFusion (2025)

**SDSFusion: A Semantic-Aware Infrared and Visible Image Fusion Network for Degraded Scenes** — TIP. [Paper](https://doi.org/10.1109/TIP.2025.3571339). Scope: supporting foundation.

**Observations and conditions:** TIR + degraded VIS; Low light; all-weather scope claimed by authors, individual weather protocols not verified.

**Mechanism and boundary:** Semantic-aware enhancement/fusion interaction; adversarial reconstruction embeds fused features into VIS refinement. Output: Fused image and enhanced VIS within coupled processing. Constraint: Semantic/multiscale guidance; exact supervised targets NR. Use as degraded-scene method. Do not add rain/snow/fog checkmarks without full protocol verification.

**Additional attributes:** task guidance.

### TDFusion (2025)

**Task-driven Image Fusion with Learnable Fusion Loss** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2025/papers/Bai_Task-driven_Image_Fusion_with_Learnable_Fusion_Loss_CVPR_2025_paper.pdf). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Meta-learned fusion loss is optimized through downstream task loss. Output: Fused image for downstream task. Constraint: Downstream detection/segmentation labels; learned fusion objective. Makes the task objective explicit; generic training does not guarantee out-of-distribution weather robustness.

**Additional attributes:** task guidance.

### TG-ECNet (2025)

**Task-Gated Multi-Expert Collaboration Network for Degraded Multi-Modal Image Fusion** — Proceedings of the 42nd International Conference on Machine Learning. [Paper](https://proceedings.mlr.press/v267/sun25k.html). Scope: weather-related.

**Observations and conditions:** V, T; H, D.

**Mechanism and boundary:** Task gates; collaborating experts. Output: Features / FI. Constraint: Clean sources; fusion loss.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

**Implementation:** [Public source](https://github.com/LeeX54946/TG-ECNet); public source link; configuration and dependencies must be checked.

### URFusion (2025)

**URFusion: Unsupervised Unified Degradation-Robust Image Fusion Network** — TIP. [Paper](https://doi.org/10.1109/TIP.2025.3607628). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; also multi-exposure inputs; Multiple degradations; individual weather types NR in inspected sources.

**Mechanism and boundary:** Separate intrinsic degradation-free content, fuse content, then assign high-quality appearance statistics. Output: Fused image. Constraint: Unsupervised; paired same-scene content extraction and high-quality appearance samples. High-quality appearance samples are a prior resource, not ground-truth fused images. Specific weather list remains unverified.

### Align-CR (2024)

**Multimodal and Multiresolution Data Fusion for High-Resolution Cloud Removal: A Novel Baseline and Benchmark** — TGRS. [Paper](https://doi.org/10.1109/TGRS.2023.3337845). Scope: weather-related.

**Observations and conditions:** S, M; C.

**Mechanism and boundary:** Progressive cross-scale alignment. Output: Features / HR optical. Constraint: Optical target; loss NR.

### BA-Fusion (2024)

**Dynamic Brightness Adaptation for Robust Multi-modal Image Fusion** — Proceedings of the International Joint Conference on Artificial Intelligence (IJCAI). [Paper](https://doi.org/10.24963/ijcai.2024/146). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; Dynamic brightness fluctuations.

**Mechanism and boundary:** Brightness-adaptive gate normalizes brightness-related channels while retaining structural channels. Output: Fused image. Constraint: Alternating training with brightness-consistency and fusion constraints. Do not confuse BA-Fusion (IJCAI image fusion) with BAFusion (Sensors LiDAR-camera detection).

**Additional attributes:** explicit conditioning; see source for training/inference scope.

### CRformer (2024)

**CRformer: Multi-modal data fusion to reconstruct cloud-free optical imagery** — International Journal of Applied Earth Observation and Geoinformation. [Paper](https://doi.org/10.1016/j.jag.2024.103793). Scope: weather-related.

**Observations and conditions:** Sentinel-1 SAR + MODIS low-resolution optical + cloudy Landsat-8 reconstruction context; realistically simulated cloud in SMILE-CR; time-series application.

**Mechanism and boundary:** Dense/sparse multi-head attention and multiscale gated feed-forward fusion. Output: cloud-free Landsat-8 multispectral product. Constraint: Cloud-free Landsat-8 targets and realistic cloud simulation. SMILE-CR uses Landsat-8/Sentinel-1/MODIS. Source identifies S1+MODIS as reconstruction inputs; cloudy Landsat is context, not assumed an independent third neural input.

### CoCoNet (2024)

**CoCoNet: Coupled Contrastive Learning Network with Multi-level Feature Ensemble for Multi-modality Image Fusion** — IJCV. [Paper](https://doi.org/10.1007/s11263-023-01952-1). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Coupled contrastive feature learning. Output: FI. Constraint: Contrastive; sources.

**Implementation:** [Public source](https://github.com/runjia0124/CoCoNet); public source link; configuration and dependencies must be checked.

### EMMA (2024)

**Equivariant Multi-Modality Image Fusion** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2024/html/Zhao_Equivariant_Multi-Modality_Image_Fusion_CVPR_2024_paper.html). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Equivariant imaging constraints. Output: Features / FI. Constraint: Self-supervised; no fused GT.

**Implementation:** [Public source](https://github.com/Zhaozixiang1228/MMIF-EMMA); public source link; configuration and dependencies must be checked.

### FENet (2024)

**Feature enhancement network for cloud removal in optical images by fusing with SAR images** — International Journal of Remote Sensing. [Paper](https://doi.org/10.1080/01431161.2023.2292014). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Feature aggregation residual and feature enhancement blocks. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

### FPNet (2024)

**Efficient Cloud Removal Network for Satellite Images Using SAR-Optical Image Fusion** — GRSL. [Paper](https://doi.org/10.1109/lgrs.2024.3397875). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Multiscale feature-pyramid fusion with efficiency objective. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

### HDRSA-Net (2024)

**HDRSA-Net: Hybrid dynamic residual self-attention network for SAR-assisted optical image cloud and shadow removal** — ISPRS Journal of Photogrammetry and Remote Sensing. [Paper](https://doi.org/10.1016/j.isprsjprs.2024.10.026). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud and shadow.

**Mechanism and boundary:** Progressive dynamic local interaction and sparse global context. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

### MRFS (2024)

**MRFS: Mutually Reinforcing Image Fusion and Segmentation** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2024/papers/Zhang_MRFS_Mutually_Reinforcing_Image_Fusion_and_Segmentation_CVPR_2024_paper.pdf). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Interactive gated mixed attention and progressive cycle attention couple image fusion with segmentation. Output: Fused image and semantic segmentation. Constraint: Source fusion objectives plus semantic segmentation labels. Weather robustness cannot be inferred solely from semantic coupling.

**Additional attributes:** task guidance.

### SCT-CR (2024)

**SCT-CR: A synergistic convolution-transformer modeling method using SAR-optical data fusion for cloud removal** — International Journal of Applied Earth Observation and Geoinformation. [Paper](https://doi.org/10.1016/j.jag.2024.103909). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Cloud-attentive synergistic convolution plus global-context transformer. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

### Text-IF (2024)

**Text-IF: Leveraging Semantic Text Guidance for Degradation-Aware and Interactive Image Fusion** — CVPR. [Paper](https://arxiv.org/abs/2403.16387). Scope: supporting foundation.

**Observations and conditions:** V, T; D^b.

**Mechanism and boundary:** Text-conditioned interactive fusion. Output: Features / FI. Constraint: Enhanced source references.

**Additional attributes:** explicit conditioning; see source for training/inference scope.

**Implementation:** [Public source](https://github.com/XunpengYi/Text-IF); public source link; configuration and dependencies must be checked.

### USSRN (2024)

**Cloud Removal With SAR-Optical Data Fusion Using a Unified Spatial–Spectral Residual Network** — TGRS. [Paper](https://doi.org/10.1109/tgrs.2023.3339210). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Unified spatial-spectral residual feature learning. Output: cloud-free optical/MS. Constraint: Not resolved from inspected abstract; retain explicit unknown. Original full-text benchmark and supervision details unresolved. Repository contains model modules but no training/evaluation entry scripts in the inspected tree.

### VIFNet (2024)

**VIFNet: An end-to-end visible–infrared fusion network for image dehazing** — Neurocomputing. [Paper](https://doi.org/10.1016/j.neucom.2024.128105). Scope: weather-related.

**Observations and conditions:** VIS + simulated infrared (band unresolved); generated NIR in RGB-only tests; H.

**Mechanism and boundary:** Multiscale inconsistency weighting. Output: Features / RGB. Constraint: Clean RGB; image/edge loss.

**Implementation:** [Public source](https://github.com/mengyu212/VIFNet_dehazing); public source link; configuration and dependencies must be checked.

### Weather-gated LRF (2024)

**Towards Robust 3D Object Detection with LiDAR and 4D Radar Fusion in Various Weather Conditions** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2024/html/Chae_Towards_Robust_3D_Object_Detection_with_LiDAR_and_4D_Radar_CVPR_2024_paper.html). Scope: weather-related.

**Observations and conditions:** L, R4, camera-derived weather features; W.

**Mechanism and boundary:** Spatial relations; radar-flow gating conditioned on pretrained visual weather features (paper Sec. 3.3, Eqs. 5–6). Output: Features / Det. Constraint: Detection supervision.

**Additional attributes:** explicit conditioning; see source for training/inference scope; task guidance.

### Attention GAN CR (2023)

**Cloud removal using SAR and optical images via attention mechanism-based GAN** — Pattern Recognition Letters. [Paper](https://doi.org/10.1016/j.patrec.2023.09.014). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; thick cloud.

**Mechanism and boundary:** SAR-to-optical translation followed by cloud-attentive adversarial reconstruction. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

**Additional attributes:** adversarial training prior.

### CDDFuse (2023)

**CDDFuse: Correlation-Driven Dual-Branch Feature Decomposition for Multi-Modality Image Fusion** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2023/html/Zhao_CDDFuse_Correlation-Driven_Dual-Branch_Feature_Decomposition_for_Multi-Modality_Image_Fusion_CVPR_2023_paper.html). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Shared/specific feature decomposition. Output: Features / FI. Constraint: Sources; correlation loss.

**Implementation:** [Public source](https://github.com/Zhaozixiang1228/MMIF-CDDFuse); public source link; configuration and dependencies must be checked.

### DATFuse (2023)

**DATFuse: Infrared and Visible Image Fusion via Dual Attention Transformer** — TCSVT. [Paper](https://doi.org/10.1109/TCSVT.2023.3234340). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No verified weather-specific protocol.

**Mechanism and boundary:** Dual-attention transformer for infrared/visible feature fusion. Output: Fused image. Constraint: NR: exact training supervision not independently read in this audit. Architecture/metadata verified from official implementation; detailed attention equations not audited.

### DIVFusion (2023)

**DIVFusion: Darkness-free infrared and visible image fusion** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2022.10.034). Scope: supporting foundation.

**Observations and conditions:** TIR + low-light VIS; Night/low illumination, texture concealment, color distortion.

**Mechanism and boundary:** Scene-illumination disentanglement precedes texture/contrast enhancement fusion with color consistency; restoration-coupled representation learning. Output: Color fused image. Constraint: Source/illumination/color constraints; no ideal fused target reported. The verified setting is darkness-free fusion; not atmospheric dehazing.

### Dif-Fusion (2023)

**Dif-Fusion: Toward High Color Fidelity in Infrared and Visible Image Fusion With Diffusion Models** — TIP. [Paper](https://doi.org/10.1109/TIP.2023.3322046). Scope: supporting foundation.

**Observations and conditions:** TIR + color VIS; No explicit weather model.

**Mechanism and boundary:** A diffusion-trained feature extractor feeds a direct fusion head; final fused-image inference does not reverse-sample an image.

**Additional attributes:** diffusion-feature prior.

### Edge-SAR (2023)

**Edge-SAR-Assisted Multimodal Fusion for Enhanced Cloud Removal** — GRSL. [Paper](https://doi.org/10.1109/lgrs.2023.3307240). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS + derived SAR edges; cloud.

**Mechanism and boundary:** Learned reconstruction with GRHED edge channels stacked with SAR and optical observations; an auxiliary structural prior, not model inversion. Output: cloud-free optical/MS. Constraint: Paired reconstruction with structural-similarity loss. Edge representations are derived features, not an independently measured third sensor.

### HS2P (2023)

**HS2P: Hierarchical spectral and structure-preserving fusion network for multimodal remote sensing image cloud and shadow removal** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2023.02.002). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud and shadow.

**Mechanism and boundary:** Hierarchical spectral/structure preservation using multi-output gradient guidance. Output: cloud-free optical/MS. Constraint: Supervised clear-optical reconstruction; follow original loss definitions.

### MT-DETR (2023)

**MT-DETR: Robust End-to-end Multimodal Detection with Confidence Fusion** — 2023 IEEE/CVF Winter Conference on Applications of Computer Vision (WACV). [Paper](https://doi.org/10.1109/wacv56688.2023.00522). Scope: weather-related.

**Observations and conditions:** camera + LiDAR + radar + temporal features; STF varied weather; synthetic paired fog augmentation.

**Mechanism and boundary:** Hierarchical residual/confidence fusion and modality-specific enhancement. Output: detections. Constraint: Task annotations; no clean fused-image target.

**Additional attributes:** task guidance.

### MetaBEV (2023)

**MetaBEV: Solving Sensor Failures for 3D Detection and Map Segmentation** — ICCV. [Paper](https://doi.org/10.1109/iccv51070.2023.00801). Scope: supporting foundation.

**Observations and conditions:** camera + LiDAR; sensor corruption/missing modalities; weather-specific evidence unresolved.

**Mechanism and boundary:** BEV-evolving attention and modality-switching training. Output: 3D detections and BEV map segmentation. Constraint: Task annotations; no clean fused-image target.

**Additional attributes:** task guidance.

### MetaFusion (2023)

**MetaFusion: Infrared and Visible Image Fusion via Meta-Feature Embedding From Object Detection** — CVPR. [Paper](https://doi.org/10.1109/CVPR52729.2023.01341). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Meta-feature embedding bridges detector semantics and fusion features; mutually promoting optimization. Output: Fused image; object detections in joint learning. Constraint: Detection labels and fusion constraints through meta-learning. A task-aware control; downstream gains must be evaluated with the detector protocol reported.

**Additional attributes:** task guidance.

**Implementation:** [Public source](https://github.com/wdzhao123/MetaFusion); inference release; training entry point not verified.

### PAIF (2023)

**PAIF: Perception-Aware Infrared-Visible Image Fusion for Attack-Tolerant Semantic Segmentation** — Proceedings of the 31st ACM International Conference on Multimedia. [Paper](https://doi.org/10.1145/3581783.3611928). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS under adversarial perturbation; Adversarial perturbations, not atmospheric weather.

**Mechanism and boundary:** Decomposition-based architecture search and adaptive adversarial learning optimize fusion for robust segmentation. Output: Fusion representation/image and segmentation. Constraint: Segmentation supervision and adversarial training. Attack robustness is a useful reliability comparison, but not evidence of fog/rain generalization.

**Additional attributes:** task guidance.

### PSFusion (2023)

**Rethinking the necessity of image fusion in high-level vision tasks: A practical infrared and visible image fusion network based on progressive semantic injection and scene fidelity** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2023.101870). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Progressive semantic injection with a source-scene restoration branch to retain scene fidelity. Output: Fused image. Constraint: Semantic guidance and source-scene/fusion constraints. Scene restoration branch is a training/design property, not evidence of removing fog or rain.

**Additional attributes:** task guidance.

### SegMiF (2023)

**Multi-interactive Feature Learning and a Full-time Multi-modality Benchmark for Image Fusion and Segmentation** — ICCV. [Paper](https://openaccess.thecvf.com/content/ICCV2023/html/Liu_Multi-interactive_Feature_Learning_and_a_Full-time_Multi-modality_Benchmark_for_Image_ICCV_2023_paper.html). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Fusion–segmentation interaction. Output: Features / FI, Seg. Constraint: Sources; semantic labels.

**Additional attributes:** task guidance.

**Implementation:** [Public source](https://github.com/JinyuanLiu-CV/SegMiF); external inference mask provenance must be resolved.

### UnCRtainTS (2023)

**UnCRtainTS: Uncertainty Quantification for Cloud Removal in Optical Satellite Time Series** — Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW). [Paper](https://doi.org/10.1109/CVPRW59228.2023.00202). Scope: weather-related.

**Observations and conditions:** S, M^t; C.

**Mechanism and boundary:** Temporal attention; uncertainty. Output: Features / MS, uncertainty. Constraint: Optical target; SAR variant.

**Implementation:** [Public source](https://github.com/PatrickTUM/UnCRtainTS); public source link; configuration and dependencies must be checked.

### DIP-HyperKite (2022)

**Hyperspectral Pansharpening Based on Improved Deep Image Prior and Residual Reconstruction** — TGRS. [Paper](https://doi.org/10.1109/tgrs.2021.3139292). Scope: supporting foundation.

**Observations and conditions:** PAN + HS; none; clear-scene foundation.

**Mechanism and boundary:** Full pipeline is mixed: observation-constrained per-image DIP upsampling precedes a directly learned HyperKite residual fusion head. Index the final fusion estimator as direct and retain model-derived preprocessing.

**Additional attributes:** model-derived DIP preprocessing; direct residual fusion; hybrid M-to-D pipeline.

**Implementation:** [Public source](https://github.com/wgcban/DIP-HyperKite); public source link; configuration and dependencies must be checked.

### DeFusion (2022)

**Fusion from Decomposition: A Self-Supervised Decomposition Approach for Image Fusion** — ECCV. [Paper](https://doi.org/10.1007/978-3-031-19797-0_41). Scope: supporting foundation.

**Observations and conditions:** IR + VIS; also photographic fusion; No explicit weather model.

**Mechanism and boundary:** Self-supervised common/unique feature decomposition and a shared reconstruction head. Output: Fused image. Constraint: Self-supervised pretext reconstruction without paired fusion training data. DeFusion (ECCV 2022) differs from DEFusion (Digital Signal Processing 2026).

### GLF-CR (2022)

**GLF-CR: SAR-enhanced cloud removal with global–local fusion** — ISPRS Journal of Photogrammetry and Remote Sensing. [Paper](https://doi.org/10.1016/j.isprsjprs.2022.08.002). Scope: weather-related.

**Observations and conditions:** S, M; C.

**Mechanism and boundary:** Global/local features; dynamic filter. Output: Features / MS. Constraint: Optical target; loss NR.

**Implementation:** [Public source](https://github.com/xufangchn/GLF-CR); public source link; configuration and dependencies must be checked.

### HydraFusion (2022)

**HydraFusion: Context-Aware Selective Sensor Fusion for Robust and Efficient Autonomous Vehicle Perception** — 2022 ACM/IEEE 13th International Conference on Cyber-Physical Systems (ICCPS). [Paper](https://doi.org/10.1109/iccps54341.2022.00013). Scope: weather-related.

**Observations and conditions:** camera + LiDAR + radar; adverse driving contexts including weather and low light.

**Mechanism and boundary:** Context gating selects sensor fusion branches. Output: detections. Constraint: Task annotations; no clean fused-image target.

**Additional attributes:** explicit conditioning; see source for training/inference scope; task guidance.

### PIAFusion (2022)

**PIAFusion: A progressive infrared and visible image fusion network based on illumination aware** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2022.03.007). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; Illumination imbalance, day/night.

**Mechanism and boundary:** Direct fusion network is trained using illumination-dependent loss weights; condition use is training-only.

**Additional attributes:** explicit conditioning; see source for training/inference scope; training-time conditioning; illumination weighting.

### ST-MVDNet (2022)

**Modality-Agnostic Learning for Radar-Lidar Fusion in Vehicle Detection** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Li_Modality-Agnostic_Learning_for_Radar-Lidar_Fusion_in_Vehicle_Detection_CVPR_2022_paper.html). Scope: supporting foundation.

**Observations and conditions:** L, R; D, missing.

**Mechanism and boundary:** Sensor augmentation; consistency. Output: Features / Det. Constraint: Detection and consistency.

**Additional attributes:** task guidance.

### SeAFusion (2022)

**Image fusion in the loop of high-level vision tasks: A semantic-aware real-time infrared and visible image fusion network** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2021.12.004). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Semantic feedback to image fusion. Output: Features / FI. Constraint: Sources; semantic labels.

**Additional attributes:** task guidance.

**Implementation:** [Public source](https://github.com/Linfeng-Tang/SeAFusion); public source link; configuration and dependencies must be checked.

### SwinFusion (2022)

**SwinFusion: Cross-domain Long-range Learning for General Image Fusion via Swin Transformer** — IEEE/CAA Journal of Automatica Sinica. [Paper](https://doi.org/10.1109/JAS.2022.105686). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Intra/cross-domain transformer interaction. Output: FI. Constraint: Source constraints.

**Implementation:** [Public source](https://github.com/Linfeng-Tang/SwinFusion); public source link; configuration and dependencies must be checked.

### TarDAL (2022)

**Target-Aware Dual Adversarial Learning and a Multi-Scenario Multi-Modality Benchmark To Fuse Infrared and Visible for Object Detection** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Liu_Target-Aware_Dual_Adversarial_Learning_and_a_Multi-Scenario_Multi-Modality_Benchmark_To_CVPR_2022_paper.html). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** One generator directly predicts the fused image; dual discriminators and bilevel detection training describe optimization/supervision, not iterative generative inference.

**Additional attributes:** task guidance; adversarial prior; detection supervision.

**Implementation:** [Public source](https://github.com/JinyuanLiu-CV/TarDAL); public source link; configuration and dependencies must be checked.

### Two-flow CR (2022)

**Cloud Removal Based on SAR-Optical Remote Sensing Data Fusion via a Two-Flow Network** — IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing. [Paper](https://doi.org/10.1109/jstars.2022.3203508). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Two-stream SAR-optical fusion network (title-level classification). Output: cloud-free optical/MS. Constraint: Not resolved from inspected abstract; retain explicit unknown. Catalogue-level inclusion; finer loss/architecture claims require original full-text verification.

### U2Fusion (2022)

**U2Fusion: A Unified Unsupervised Image Fusion Network** — TPAMI. [Paper](https://doi.org/10.1109/TPAMI.2020.3012548). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Unified unsupervised fusion representation. Output: FI. Constraint: Source constraints.

**Implementation:** [Public source](https://github.com/hanna-xu/U2Fusion); public source link; configuration and dependencies must be checked.

### UMF-CMGR (2022)

**Unsupervised Misaligned Infrared and Visible Image Fusion via Cross-Modality Image Generation and Registration** — Proceedings of the International Joint Conference on Artificial Intelligence (IJCAI). [Paper](https://doi.org/10.24963/ijcai.2022/487). Scope: supporting foundation.

**Observations and conditions:** Misaligned TIR + VIS; Geometric misalignment, not weather-specific.

**Mechanism and boundary:** VIS-to-pseudo-IR translation enables same-modality registration before dual-path feature interaction fusion. Output: Registered/fused image. Constraint: Unsupervised registration/fusion; generated deformations and source constraints. Pseudo-IR is an intermediate registration aid, not an independently observed extra sensor.

**Additional attributes:** generated registration intermediate.

### All-season CR (2021)

**Multisensor Data Fusion for Cloud Removal in Global and All-Season Sentinel-2 Imagery** — TGRS. [Paper](https://doi.org/10.1109/TGRS.2020.3024744). Scope: weather-related.

**Observations and conditions:** S, M; C.

**Mechanism and boundary:** Multisensor adversarial optical reconstruction. Output: MS. Constraint: Optical target.

**Additional attributes:** adversarial training prior.

### MVDNet (2021)

**Robust Multimodal Vehicle Detection in Foggy Weather Using Complementary Lidar and Radar Signals** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2021/html/Qian_Robust_Multimodal_Vehicle_Detection_in_Foggy_Weather_Using_Complementary_Lidar_CVPR_2021_paper.html). Scope: weather-related.

**Observations and conditions:** L, R; H_sim.

**Mechanism and boundary:** Region-wise complementary sensor fusion. Output: Regions / Det. Constraint: Detection supervision.

**Additional attributes:** task guidance.

### RFN-Nest (2021)

**RFN-Nest: An end-to-end residual fusion network for infrared and visible images** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2021.02.023). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Multiscale nested autoencoder followed by learnable residual fusion networks. Output: Fused image. Constraint: Two-stage autoencoder reconstruction and source-constrained fusion. Replaces fixed feature fusion rules; no weather-specific inference is claimed.

### SDNet (2021)

**SDNet: A Versatile Squeeze-and-Decomposition Network for Real-Time Image Fusion** — IJCV. [Paper](https://doi.org/10.1007/s11263-021-01501-8). Scope: supporting foundation.

**Observations and conditions:** IR + VIS; also photographic/medical fusion; No explicit weather model.

**Mechanism and boundary:** Fusion squeeze followed by source decomposition; gradient/intensity objectives retain scene information. Output: Fused image. Constraint: Unsupervised source reconstruction and gradient/intensity constraints. Source decomposition is not synonymous with separating weather from scene.

### STDFusionNet (2021)

**STDFusionNet: An Infrared and Visible Image Fusion Network Based on Salient Target Detection** — IEEE Transactions on Instrumentation and Measurement. [Paper](https://doi.org/10.1109/TIM.2021.3075747). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Salient-target masks spatially guide source information selection through the training loss. Output: Fused image. Constraint: Salient-target masks during training; masks not required at inference. Task/saliency supervision is training-only; no inference-time condition input or joint detector training is implied.

**Additional attributes:** task guidance; training-only salient-target annotations.

**Implementation:** [Public source](https://github.com/Linfeng-Tang/STDFusionNet); public source link; configuration and dependencies must be checked.

### CMD (2020)

**Thick Cloud Removal With Optical and SAR Imagery via Convolutional-Mapping-Deconvolutional Network** — TGRS. [Paper](https://doi.org/10.1109/tgrs.2019.2956959). Scope: weather-related.

**Observations and conditions:** low-resolution heterogeneous optical reference + SAR + cloudy high-resolution optical for normalization and compositing; thick cloud.

**Mechanism and boundary:** Convolutional encoding, feature-space mapping, deconvolution, clear-area intensity normalization and cloud-pixel replacement. Output: cloud-free high-resolution optical. Constraint: Paired clear high-resolution patches and low-resolution optical/SAR references. Formal TGRS58(4) publication April2020; DOI and online publication2019. Preserve auxiliary optical input and compositing stage.

### DDcGAN (2020)

**DDcGAN: A Dual-Discriminator Conditional Generative Adversarial Network for Multi-Resolution Image Fusion** — TIP. [Paper](https://doi.org/10.1109/TIP.2020.2977573). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS, possibly different resolution; Resolution mismatch, not weather-specific.

**Mechanism and boundary:** Dual source discriminators and content loss; downsampled fused consistency handles low-resolution IR. Output: High-resolution fused image. Constraint: Adversarial and source content supervision; no ideal fused image. Generator training is not a physical model of weather or a weather-restoration guarantee.

**Additional attributes:** adversarial training prior.

### DIDFuse (2020)

**DIDFuse: Deep Image Decomposition for Infrared and Visible Image Fusion** — Proceedings of the International Joint Conference on Artificial Intelligence (IJCAI). [Paper](https://doi.org/10.24963/ijcai.2020/135). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; NIR examples in repository; No explicit weather model.

**Mechanism and boundary:** Autoencoder separates similar background and dissimilar detail representations. Output: Fused image. Constraint: Source reconstruction and background/detail separation constraints. Learned decomposition is a useful control for weather-corrupted detail, but the original method does not identify weather components.

### DSen2-CR (2020)

**Cloud removal in Sentinel-2 imagery using a deep residual neural network and SAR-optical data fusion** — ISPRS Journal of Photogrammetry and Remote Sensing. [Paper](https://doi.org/10.1016/j.isprsjprs.2020.05.013). Scope: weather-related.

**Observations and conditions:** S, M; C.

**Mechanism and boundary:** Input concatenation; residual network. Output: Input / MS. Constraint: Cloud-adaptive target loss.

**Additional attributes:** cloud-dependent training objective.

**Implementation:** [Public source](https://github.com/ameraner/dsen2-cr); public source link; configuration and dependencies must be checked.

### FusionDN (2020)

**FusionDN: A Unified Densely Connected Network for Image Fusion** — AAAI. [Paper](https://doi.org/10.1609/aaai.v34i07.6936). Scope: supporting foundation.

**Observations and conditions:** IR + VIS; also other fusion tasks; No explicit weather model.

**Mechanism and boundary:** Dense network with source-quality/information weighting and elastic weight consolidation across fusion tasks. Output: Fused image. Constraint: Unsupervised similarity constraints weighted by source quality. Quality weighting supports adaptation conceptually, without verified weather-specific tests in the inspected abstract.

**Additional attributes:** quality-weighted training objective.

### IFCNN (2020)

**IFCNN: A general image fusion framework based on convolutional neural network** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2019.07.011). Scope: supporting foundation.

**Observations and conditions:** IR + VIS; also other image-fusion inputs; No explicit weather model.

**Mechanism and boundary:** CNN feature extraction and elementwise fusion with convolutional reconstruction. Output: Fused image. Constraint: Supervised multifocus pretraining; transfer to IR-VIS without fused IR-VIS targets. Generic fusion baseline; training on synthetic multifocus data is not weather robustness evidence.

### NestFuse (2020)

**NestFuse: An Infrared and Visible Image Fusion Architecture Based on Nest Connection and Spatial/Channel Attention Models** — IEEE Transactions on Instrumentation and Measurement. [Paper](https://doi.org/10.1109/TIM.2020.3005230). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; No explicit weather model.

**Mechanism and boundary:** Nested decoder with spatial and channel attention fusion of multiscale features. Output: Fused image. Constraint: Autoencoder reconstruction on MS-COCO; designed attention fusion. Generic complementary-feature aggregation; not a denoising or deweathering model.

### PMGI (2020)

**Rethinking the Image Fusion: A Fast Unified Image Fusion Network based on Proportional Maintenance of Gradient and Intensity** — AAAI. [Paper](https://doi.org/10.1609/aaai.v34i07.6975). Scope: supporting foundation.

**Observations and conditions:** IR + VIS; also PAN-MS and photographic tasks; No explicit weather model.

**Mechanism and boundary:** Gradient and intensity paths exchange features through a pathwise transfer block. Output: Fused image. Constraint: Source gradient/intensity constraints; task-dependent loss weights. A unified architecture does not establish one fixed checkpoint for every degradation.

### Seeing Through Fog (2020)

**Seeing Through Fog Without Seeing Fog: Deep Multimodal Sensor Fusion in Unseen Adverse Weather** — CVPR. [Paper](https://openaccess.thecvf.com/content_CVPR_2020/html/Bijelic_Seeing_Through_Fog_Without_Seeing_Fog_Deep_Multimodal_Sensor_Fusion_CVPR_2020_paper.html). Scope: weather-related.

**Observations and conditions:** Multi^d; R, H, S.

**Mechanism and boundary:** Measurement-entropy-steered feature fusion; reliability conditioning. Output: Features / Det. Constraint: Detection supervision.

**Additional attributes:** explicit conditioning; see source for training/inference scope; task guidance.

### Simulation-fusion (2020)

**Cloud Removal with Fusion of High Resolution Optical and SAR Images Using Generative Adversarial Networks** — Remote Sensing. [Paper](https://doi.org/10.3390/rs12010191). Scope: weather-related.

**Observations and conditions:** S, M; C.

**Mechanism and boundary:** SAR simulation followed by adversarial fusion. Output: MS. Constraint: Optical target.

**Additional attributes:** adversarial training prior.

### DenseFuse (2019)

**DenseFuse: A Fusion Approach to Infrared and Visible Images** — TIP. [Paper](https://doi.org/10.1109/TIP.2018.2887342). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Dense encoder; feature aggregation. Output: Features / FI. Constraint: Autoencoder reconstruction.

**Implementation:** [Public source](https://github.com/hli1221/imagefusion_densefuse); public source link; configuration and dependencies must be checked.

### FusionGAN (2019)

**FusionGAN: A generative adversarial network for infrared and visible image fusion** — Information Fusion. [Paper](https://doi.org/10.1016/j.inffus.2018.09.004). Scope: supporting foundation.

**Observations and conditions:** V, T; –.

**Mechanism and boundary:** Adversarial image fusion. Output: FI. Constraint: Adversarial; sources.

**Additional attributes:** adversarial training prior.

### SAR-Opt-cGAN (2018)

**A Conditional Generative Adversarial Network to Fuse SAR and Multispectral Optical Data for Cloud Removal from Sentinel-2 Images** — Proceedings of the IEEE International Geoscience and Remote Sensing Symposium (IGARSS). [Paper](https://doi.org/10.1109/IGARSS.2018.8519215). Scope: weather-related.

**Observations and conditions:** S, M; C, H.

**Mechanism and boundary:** Conditional adversarial synthesis. Output: Input / MS. Constraint: Optical target; adversary.

**Additional attributes:** adversarial training prior.

### PanNet (2017)

**PanNet: A Deep Network Architecture for Pan-Sharpening** — ICCV. [Paper](https://doi.org/10.1109/iccv.2017.193). Scope: supporting foundation.

**Observations and conditions:** PAN + MS; none; clear-scene foundation.

**Mechanism and boundary:** Residual high-frequency detail learning and spectral skip connection. Output: high-resolution MS. Constraint: Spatial-degradation reconstruction protocol; no weather-training claim.

**Implementation:** [Public source](https://github.com/liangjiandeng/DLPan-Toolbox); third-party DLPan benchmark implementation.

### PNN (2016)

**Pansharpening by Convolutional Neural Networks** — Remote Sensing. [Paper](https://doi.org/10.3390/rs8070594). Scope: supporting foundation.

**Observations and conditions:** PAN + MS; none; clear-scene foundation.

**Mechanism and boundary:** Supervised convolutional spatial-spectral reconstruction. Output: high-resolution MS. Constraint: Spatial-degradation reconstruction protocol; no weather-training claim.

**Implementation:** [Public source](https://github.com/liangjiandeng/DLPan-Toolbox); third-party DLPan benchmark implementation.

## Iterative generative estimation

### AGFlow (2026)

**Asynchronous Remote Sensing Time-Series Fusion for Cloud Removal and Anytime Reconstruction** — Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops. [Paper](https://openaccess.thecvf.com/content/CVPR2026W/MORSE/papers/Fallah_Asynchronous_Remote_Sensing_Time-Series_Fusion_for_Cloud_Removal_and_Anytime_CVPRW_2026_paper.pdf). Scope: weather-related.

**Observations and conditions:** asynchronous SAR time series + optical time series + observation dates; cloud and missing observations.

**Mechanism and boundary:** Timestamp-conditioned spatiotemporal flow matching with internal SAR-optical temporal cross-attention. Output: optical temporal sequence. Constraint: Cloud-free temporal targets with masking; unobserved-date NDVI validation differs from pixel-reference evaluation. CVPR2026 MORSE Workshop. Queries lacking aligned Sentinel-2 ground truth use regional NDVI trends against RapidAI4EO, not strict pixel-wise matching.

**Additional attributes:** explicit conditioning.

### DRFusion (2026)

**Degradation-Robust Fusion: An Efficient Degradation-Aware Diffusion Framework for Multimodal Image Fusion in Arbitrary Degradation Scenarios** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2026/html/Shi_Degradation-Robust_Fusion_An_Efficient_Degradation-Aware_Diffusion_Framework_for_Multimodal_Image_CVPR_2026_paper.html). Scope: supporting foundation.

**Observations and conditions:** V, T; D.

**Mechanism and boundary:** Time-indexed denoising, joint observation correction and DDIM update execute in a Step loop; fused-image regression is the per-step parameterization, not direct one-pass fusion.

**Additional attributes:** joint observation correction; degradation-aware diffusion.

**Implementation:** [Public source](https://github.com/YShi-cool/DRFusion); public source link; configuration and dependencies must be checked.

### DSPFusion (2026)

**DSPFusion: Image Fusion via Degradation and Semantic Dual-Prior Guidance** — TIP. [Paper](https://doi.org/10.1109/TIP.2026.3700938). Scope: weather-related.

**Observations and conditions:** V, T; R, D.

**Mechanism and boundary:** Degradation and semantic latent priors. Output: Latent / FI. Constraint: Enhanced sources; priors.

**Implementation:** [Public source](https://github.com/Linfeng-Tang/DSPFusion); public source link; configuration and dependencies must be checked.

### GLCdiffcr (2026)

**A global-local interaction and conditional consistency constrained diffusion model for SAR-guided optical image cloud removal** — International Journal of Applied Earth Observation and Geoinformation. [Paper](https://doi.org/10.1016/j.jag.2025.105013). Scope: weather-related.

**Observations and conditions:** S, M; C.

**Mechanism and boundary:** Diffusion; conditional consistency. Output: Sampling / optical. Constraint: Target construction NR.

### Mask-DiFuser (2026)

**Mask-DiFuser: A Masked Diffusion Model for Unified Unsupervised Image Fusion** — TPAMI. [Paper](https://doi.org/10.1109/TPAMI.2025.3609323). Scope: supporting foundation.

**Observations and conditions:** TIR + VIS; NIR + VIS; other general fusion tasks; General fusion; night/NIR examples, no verified weather-specialist claim.

**Mechanism and boundary:** Dual masked image reconstruction learns a conditional diffusion fusion prior from natural images. Output: Fused image. Constraint: Self-supervised dual masking; no ideal multimodal fused targets. Final issue year 2026; online acceptance/publication 2025. One paper, not two annual entries.

**Additional attributes:** global semantic encoder; not automatically a downstream-task loss.

### ReCoFuse (2026)

**ReCoFuse: Ultra-Robust Image Fusion via Restorative Multi-Modal Diffusion Reciprocal Coupling** — CVPR. [Paper](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_ReCoFuse_Ultra-Robust_Image_Fusion_via_Restorative_Multi-Modal_Diffusion_Reciprocal_Coupling_CVPR_2026_paper.html). Scope: weather-related.

**Observations and conditions:** V, T; H, D.

**Mechanism and boundary:** Reciprocal cross-modal diffusion. Output: Sampling / FI. Constraint: Regularization; targets NR.

**Implementation:** [Public source](https://github.com/HaoZhang1018/ReCoFuse); public source link; configuration and dependencies must be checked.

### DB-CR (2025)

**Multimodal Diffusion Bridge With Attention-Based SAR Fusion for Satellite Image Cloud Removal** — TGRS. [Paper](https://doi.org/10.1109/tgrs.2025.3604654). Scope: weather-related.

**Observations and conditions:** SAR + cloudy optical/MS; cloud.

**Mechanism and boundary:** Diffusion bridge from cloudy to cloud-free distribution; cross-modal attention. Output: cloud-free optical/MS. Constraint: Cloud-free optical reconstruction targets; diffusion training.

### EMRDM (2025)

**Effective Cloud Removal for Remote Sensing Images by an Improved Mean-Reverting Denoising Model with Elucidated Design Space** — CVPR. [Paper](https://doi.org/10.1109/cvpr52734.2025.01663). Scope: weather-related.

**Observations and conditions:** cloudy Sentinel-2 optical/MS + Sentinel-1 SAR in SEN12MS-CR; optical time series in separate benchmarks; cloud.

**Mechanism and boundary:** Mean-reverting diffusion with redesigned denoiser and sampling. Output: cloud-free13-band optical in SEN12MS-CR configuration. Constraint: Supervised mean-reverting diffusion against clear optical targets. Original CVPR paper explicitly evaluates auxiliary SAR. Optical-only experiments use different input budgets.

**Implementation:** [Public source](https://github.com/Ly403/EMRDM); public source link; configuration and dependencies must be checked.

### MMAIF (2025)

**MMAIF: Multi-task and Multi-degradation All-in-One for Image Fusion with Language Guidance** — ICCV. [Paper](https://openaccess.thecvf.com/content/ICCV2025/html/Cao_MMAIF_Multi-task_and_Multi-degradation_All-in-One_for_Image_Fusion_with_Language_ICCV_2025_paper.html). Scope: weather-related.

**Observations and conditions:** V, T^c; R, H, S, D.

**Mechanism and boundary:** Two distinct variants: direct regression (D) and iterative flow matching (G). A single paper is indexed under its flow variant for counts, while both variants remain explicit in the catalogue and experiments.

**Additional attributes:** D/G variants; language conditioning; flow-indexed paper count; explicit conditioning.

**Implementation:** [Public source](https://github.com/294coder/MMAIF); public source link; configuration and dependencies must be checked.

### OmniFuse (2025)

**OmniFuse: Composite Degradation-Robust Image Fusion With Language-Driven Semantics** — TPAMI. [Paper](https://doi.org/10.1109/TPAMI.2025.3568433). Scope: supporting foundation.

**Observations and conditions:** V, T; D.

**Mechanism and boundary:** Language-conditioned diffusion fusion. Output: FI. Constraint: NR.

**Additional attributes:** explicit conditioning.

**Implementation:** [Public source](https://github.com/HaoZhang1018/OmniFuse); public source link; configuration and dependencies must be checked.

### RESTORE-DiT (2025)

**RESTORE-DiT: Reliable satellite image time series reconstruction by multimodal sequential diffusion transformer** — Remote Sensing of Environment. [Paper](https://doi.org/10.1016/j.rse.2025.114872). Scope: weather-related.

**Observations and conditions:** SAR time series + cloudy optical time series + observation dates; cloud.

**Mechanism and boundary:** Date-conditioned diffusion transformer for multimodal time series. Output: optical temporal sequence. Constraint: Cloud-free optical reconstruction targets; diffusion training.

**Additional attributes:** explicit conditioning.

### SARDiff-CR (2025)

**Efficient Diffusion Model for SAR-Assisted Optical Remote Sensing Image Cloud Removal** — Proceedings of the IEEE International Geoscience and Remote Sensing Symposium (IGARSS). [Paper](https://doi.org/10.1109/IGARSS55030.2025.11243696). Scope: weather-related.

**Observations and conditions:** S, M; C.

**Mechanism and boundary:** Latent diffusion; cross-domain interaction. Output: MS. Constraint: Optical target.

### DRMF (2024)

**DRMF: Degradation-Robust Multi-Modal Image Fusion via Composable Diffusion Prior** — Proceedings of the ACM International Conference on Multimedia. [Paper](https://doi.org/10.1145/3664647.3681064). Scope: supporting foundation.

**Observations and conditions:** V, T; D.

**Mechanism and boundary:** Composable modality-specific priors. Output: Sampling / FI. Constraint: Clean/enhanced references.

**Implementation:** [Public source](https://github.com/Linfeng-Tang/DRMF); public source link; configuration and dependencies must be checked.

### DiffCR (2024)

**DiffCR: A Fast Conditional Diffusion Framework for Cloud Removal From Optical Satellite Images** — TGRS. [Paper](https://doi.org/10.1109/tgrs.2024.3365806). Scope: supporting foundation.

**Observations and conditions:** multitemporal optical (original setting); cloud.

**Mechanism and boundary:** Decoupled condition encoder and time-condition fusion for diffusion. Output: cloud-free optical. Constraint: Supervised optical-target conditional diffusion. Original paper evaluates two optical multi-temporal datasets. Current repository adds a later SEN12MS-CR extension; do not attribute that extension to the original paper.

### Text-DiFuse (2024)

**Text-DiFuse: An Interactive Multi-Modal Image Fusion Framework based on Text-modulated Diffusion Model** — NeurIPS. [Paper](https://papers.nips.cc/paper_files/paper/2024/hash/45e409b46bebd648e9041a628a1a9964-Abstract-Conference.html). Scope: supporting foundation.

**Observations and conditions:** V, T; D.

**Mechanism and boundary:** Text-conditioned diffusion fusion. Output: FI. Constraint: NR.

**Additional attributes:** explicit conditioning.

**Implementation:** [Public source](https://github.com/Leiii-Cao/Text-DiFuse); public source link; configuration and dependencies must be checked.

### DDFM (2023)

**DDFM: Denoising Diffusion Model for Multi-Modality Image Fusion** — ICCV. [Paper](https://openaccess.thecvf.com/content/ICCV2023/html/Zhao_DDFM_Denoising_Diffusion_Model_for_Multi-Modality_Image_Fusion_ICCV_2023_paper.html). Scope: supporting foundation.

**Observations and conditions:** IR + VIS; also medical modalities; No explicit weather model.

**Mechanism and boundary:** Pretrained unconditional diffusion prior combines with likelihood-driven fusion via expectation maximization. Output: Fused image. Constraint: Pretrained DDPM plus inference-time likelihood fusion; no fusion fine-tuning. Diffusion denoising steps are sampling operations; they do not establish weather-removal supervision.

**Implementation:** [Public source](https://github.com/Zhaozixiang1228/MMIF-DDFM); public source link; configuration and dependencies must be checked.

### DDPM-Fus (2023)

**Hyperspectral and Multispectral Image Fusion Using the Conditional Denoising Diffusion Probabilistic Model** — arXiv preprint. [Paper](https://doi.org/10.48550/arXiv.2307.03423). Scope: supporting foundation.

**Observations and conditions:** HS + MS; none; clear-scene foundation.

**Mechanism and boundary:** Conditional denoising diffusion spatial-spectral fusion. Output: high-resolution HS. Constraint: Supervised conditional diffusion against high-resolution hyperspectral targets. The 2023 preprint is kept distinct from differently titled later work. No weather experiment is claimed.
