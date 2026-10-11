# Datasets and benchmarks

[Home](../README.md) · [Machine-readable inventory](../data/datasets.csv)

This inventory distinguishes real acquisition, synthetic degradation/simulation, conventional controls, and boundary resources. **NR** means not reported or not verified in the cited sources. Counts retain their original units; pairs, images, patches, frames, sequences, and regions must not be added as if equivalent. Related releases can share observations. Data access, data licensing, code licensing, alignment, and clean-reference availability are independent properties. R/S/C denote real acquisition, synthetic generation, and conventional controls. Some boundary resources (for example, ACDC and RICE) do not provide the complementary measured modalities required for a multimodal fusion benchmark.

## VIS–infrared image fusion and controls

### AWMM-100K

[Primary resource](https://ixilai.github.io/AWMM-100K/)

- **Modalities and sampling:** VIS + TIR. Resolution NR.
- **Origin and conditions:** S+R; rain, haze, snow; three strengths.
- **Scale and split:** Paper: 100,000 pairs; website: >187,699 images. Frozen full split NR.
- **References, alignment, and labels:** Pre-degradation sources for S; real clean pairing NR. Registration inherited from parents. Weather labels.
- **Access and qualifications:** Author download route; data license NR. Parent overlap and unit/version mismatch require audit.

### AWMM-Text

[Primary resource](https://ixilai.github.io/AWMM-100K/)

- **Modalities and sampling:** VIS + TIR + text.
- **Origin and conditions:** Derived from AWMM; real/synthetic proportions NR.
- **Scale and split:** 8,500 pairs with corresponding clean images. Split NR.
- **References, alignment, and labels:** Inherited alignment; global/fine descriptions generated with BLIP and ChatGPT-4, then screened. No unique fused target.
- **Access and qualifications:** Author project update dated May 25, 2026; license NR. Related subset, not 8,500 independent new scenes.

### DeMMI-RF

[Primary resource](https://github.com/LeeX54946/TG-ECNet)

- **Modalities and sampling:** VIS + TIR.
- **Origin and conditions:** S on real parents; haze, noise, defocus, stripes. Only haze is weather.
- **Scale and split:** Training: 35,418 restoration / 26,631 fusion samples; testing: 9,895 plus 510 compound samples.
- **References, alignment, and labels:** Source references and degradation labels; inherited registration. Counts follow task-specific author tables.
- **Access and qualifications:** Author cloud-drive routes; data license NR. Do not sum task rows as independent scenes.

### EMS-Lite / Full

[Primary resource](https://github.com/XunpengYi/EMS)

- **Modalities and sampling:** VIS + TIR; text for Lite.
- **Origin and conditions:** Mixed real/synthetic degradation. Full includes rain/haze; Lite emphasizes illumination, contrast, noise.
- **Scale and split:** Total and split NR.
- **References, alignment, and labels:** Some high-quality targets are algorithmic/manual pseudo-references. Parents include MFNet, RoadScene, LLVIP.
- **Access and qualifications:** Lite route verified; Full release requires archive verification. Data license NR; parent rights apply.

### FMB

[Primary resource](https://github.com/JinyuanLiu-CV/SegMiF)

- **Modalities and sampling:** VIS + TIR.
- **Origin and conditions:** R; includes dense fog, heavy rain, low illumination.
- **Scale and split:** 1,500 pairs; commonly used 1,220 tr / 280 te; verify file lists.
- **References, alignment, and labels:** Registered pairs; semantic labels. No clean/fused GT.
- **Access and qualifications:** Author SegMiF drives; license NR. Weather-specific counts and frozen weather split NR.

### M3FD

[Primary resource](https://github.com/JinyuanLiu-CV/TarDAL)

- **Modalities and sampling:** VIS + TIR.
- **Origin and conditions:** R; day, overcast, night, challenge.
- **Scale and split:** 4,200 detection/fusion pairs; repository additionally lists 300 fusion pairs. Release-specific splits.
- **References, alignment, and labels:** Synchronized, calibrated, homography registered; current repository: 34,407 boxes, six classes. No fused GT.
- **Access and qualifications:** Author TarDAL drives; data license NR. Repository GPL does not establish data rights; extra-300 overlap must be checked.

### MSRS

[Primary resource](https://github.com/Linfeng-Tang/MSRS)

- **Modalities and sampling:** VIS + enhanced TIR.
- **Origin and conditions:** R, C; day/night, not a verified weather benchmark.
- **Scale and split:** 1,444 pairs: 715 day / 729 night; 1,083 tr / 361 te directory protocol.
- **References, alignment, and labels:** Removes 125 misaligned MFNet pairs; inherited semantic labels. TIR is processed, not raw radiometry.
- **Access and qualifications:** Author train/test downloads; license NR. Shares parent observations with MFNet.

### RoadScene

[Primary resource](https://github.com/hanna-xu/RoadScene)

- **Modalities and sampling:** VIS + TIR.
- **Origin and conditions:** R, C; FLIR-derived video frames. Weather labels NR.
- **Scale and split:** 221 pairs. Unified tr/te split NR.
- **References, alignment, and labels:** Thermal denoising, precise registration and cropping; task labels NR. No clean/fused GT.
- **Access and qualifications:** Author repository; license NR. Pair count is not independent-video count.

### TNO (2022 release)

[Primary resource](https://figshare.com/articles/dataset/TNO_Image_Fusion_Dataset/1008029)

- **Modalities and sampling:** Intensified VIS, NIR, LWIR across camera systems.
- **Origin and conditions:** R, C; night scenes; unified weather protocol NR.
- **Scale and split:** Full count NR. Often-used 21/24-pair subsets are not the complete release.
- **References, alignment, and labels:** Registration is system-dependent; inspect acquisition folders. Unified task labels/split NR.
- **Access and qualifications:** Figshare; CC BY 4.0 with attribution instructions. Distinguish 2014 v1 and 2022 v2.

### LLVIP

[Primary resource](https://bupt-ai-cz.github.io/LLVIP/)

- **Modalities and sampling:** VIS + TIR.
- **Origin and conditions:** R, C; low illumination.
- **Scale and split:** 15,488 pairs (30,976 images); 12,025 tr / 3,463 te.
- **References, alignment, and labels:** Author-stated temporal/spatial alignment; pedestrian boxes; raw data also available. No clean-daylight target.
- **Access and qualifications:** Author project downloads; noncommercial use stated. Correlated video frames require scene-aware splits.

### MFNet

[Primary resource](https://github.com/haqishen/MFNet-pytorch)

- **Modalities and sampling:** RGB + TIR; four-channel observations.
- **Origin and conditions:** R, C; day/night. Weather strata NR.
- **Scale and split:** 1,569 samples: 820 day / 749 night. Exact split counts NR.
- **References, alignment, and labels:** Semantic labels; some misalignment, as documented by MSRS filtering. No fused GT.
- **Access and qualifications:** Author project/repository; license NR. Parent of MSRS, not an independent test domain.

### FLIR ADAS

[Primary resource](https://oem.flir.com/en-in/solutions/automotive/adas-dataset-form/)

- **Modalities and sampling:** RGB + TIR.
- **Origin and conditions:** R; weather-specific quotas NR.
- **Scale and split:** 26,442 frames: 9,711 TIR + 9,233 RGB stills + 7,498 video frames. Recommended tr/va.
- **References, alignment, and labels:** 520,000 boxes, 15 classes. Video matching does not imply all stills are pixel-aligned pairs.
- **Access and qualifications:** Provider form/agreement; full terms NR. Distinguish earlier 14,452-frame versions.

### AirSim-VID

[Primary resource](https://github.com/mengyu212/VIFNet_dehazing)

- **Modalities and sampling:** Simulated hazy VIS, clear VIS, IR; IR spectral band NR.
- **Origin and conditions:** S scene and fog; AirSimNH; three fog strengths.
- **Scale and split:** 2,310 aligned groups. Tr/va/te manifest and counts NR.
- **References, alignment, and labels:** Co-located simulated cameras; 5 m path sampling; clear VIS target. Semantic/detection labels NR.
- **Access and qualifications:** Author VIFNet drive; license NR. Group related poses and weather variants; simulated IR is not measured TIR.

### SWVI / SWVID

[Primary resource](https://github.com/lhy-zju/CFMW)

- **Modalities and sampling:** VIS + TIR + weather-affected VIS.
- **Origin and conditions:** R parents + S rain/fog/snow; day/night.
- **Scale and split:** 2025: 64,281 pairs; listed tr/va/te 34,280/17,140/8,570 sum to 59,990; repository: 60K.
- **References, alignment, and labels:** Inherited alignment; pre-weather VIS target and detection labels. Current class/box mapping NR.
- **Access and qualifications:** Author Hugging Face archive, about 20 GB; data license NR. Code AGPL does not establish parent-data rights.

### FOGIV

[Primary resource](https://github.com/XiangheBi/FIVFusion)

- **Modalities and sampling:** VIS, TIR; source-aligned M3FD images.
- **Origin and conditions:** S; atmospheric-scattering fog at two density levels.
- **Scale and split:** 1,540 source groups, each with two fog versions; 1,500 train / 40 test.
- **References, alignment, and labels:** Pre-fog VIS and TIR sources; no physical fused target. Retain source identity across severity variants.
- **Access and qualifications:** Author repository links a Baidu archive; download contents and data license NR. M3FD-derived: prevent parent-image leakage and do not count severities as independent scenes.

## Multimodal adverse-weather perception

### MUSES

[Primary resource](https://github.com/timbroed/MUSES)

- **Modalities and sampling:** RGB, LiDAR, radar, event, IMU/GNSS. No TIR.
- **Origin and conditions:** R; clear, rain, fog, snow; day/night.
- **Scale and split:** 2,500 scenes; 1,500 tr / 250 va / 750 te; geographic separation.
- **References, alignment, and labels:** Calibrated synchronization, projection and motion compensation; panoptic labels, uncertainty masks. Daytime revisits are not pixel GT.
- **Access and qualifications:** Author website/SDK; custom noncommercial license, access conditions require checking. Test labels withheld.

### Seeing Through Fog

[Primary resource](https://github.com/princeton-computational-imaging/SeeingThroughFog)

- **Modalities and sampling:** Stereo RGB, gated NIR, LiDAR, radar.
- **Origin and conditions:** R road + physical fog chamber; fog/rain/snow.
- **Scale and split:** 12,000 road samples + 1,500 chamber measurements; about 100K object labels.
- **References, alignment, and labels:** Calibrated projection; 2D/3D boxes and condition tags. Road clean pairing absent; chamber pairing sequence-dependent.
- **Access and qualifications:** Author SDK/downloads; data license NR. DENSE is the associated project family, not a duplicate dataset.

### RADIATE

[Primary resource](https://pro.hw.ac.uk/radiate/)

- **Modalities and sampling:** Scanning radar, stereo RGB, 32-channel LiDAR, GPS/IMU.
- **Origin and conditions:** R; sun, night, rain, fog, snow.
- **Scale and split:** Three annotated hours; >200,000 actor instances. Good/mixed-weather protocols.
- **References, alignment, and labels:** Calibration and time information; eight actor categories, boxes/tracks. No clean image GT.
- **Access and qualifications:** Registered author download; CC BY-NC-SA 4.0. Instances are not frames; radar is not SAR.

### CADC

[Primary resource](https://github.com/mpitropov/cadc_devkit)

- **Modalities and sampling:** Eight RGB cameras, 32-beam LiDAR, GNSS/INS.
- **Origin and conditions:** R; varying winter/snow conditions.
- **Scale and split:** 7,000 annotated synchronized frames. Drive-based release; unified split counts NR.
- **References, alignment, and labels:** Intrinsic/extrinsic calibration; 3D object/tracking cuboids. No clean image GT.
- **Access and qualifications:** Author devkit scripts; CC BY-NC 4.0. CADC/CADCD naming does not denote two datasets.

### K-Radar

[Primary resource](https://github.com/kaist-avelab/K-Radar)

- **Modalities and sampling:** 4D radar tensor, LiDAR, stereo cameras, RTK-GPS.
- **Origin and conditions:** R; fog, rain, snow and varied roads.
- **Scale and split:** Approximately 35K frames. Official split/label version must be fixed.
- **References, alignment, and labels:** Calibrated sensors; 3D boxes, weather/road metadata. No clean image GT.
- **Access and qualifications:** KAIST author repository; data license NR. Radar dimensions are Doppler, range, azimuth, elevation.

### Boreas

[Primary resource](https://registry.opendata.aws/boreas/)

- **Modalities and sampling:** RGB, 128-beam LiDAR, scanning radar, GNSS poses.
- **Origin and conditions:** R; rain, snowfall, seasonal variation.
- **Scale and split:** 44 paper sequences; >350 km. Task-specific odometry, localization, and object splits.
- **References, alignment, and labels:** Calibration and accurate poses; repeated routes have scene changes, not simultaneous clean references.
- **Access and qualifications:** AWS Open Data and author SDK; CC BY 4.0. Distance, sequences, and frames are distinct units.

### ACDC

[Primary resource](https://arxiv.org/abs/2104.13395)

- **Modalities and sampling:** RGB only.
- **Origin and conditions:** R; fog, night, rain, snow.
- **Scale and split:** 4,006 adverse images plus 4,006 normal-condition correspondences. Split counts NR here.
- **References, alignment, and labels:** Semantic labels and invalid/uncertain regions; normal-condition revisits, not strict pixel GT.
- **Access and qualifications:** Author project/paper; license NR. Weather/perception context, not a multisensor fusion dataset.

### DeLiVER

[Primary resource](https://jamycheung.github.io/DELIVER.html)

- **Modalities and sampling:** RGB, depth/HHA, LiDAR, events; six views. Paper image size 1042×1042; released model configs commonly use 1024×1024.
- **Origin and conditions:** S simulator; cloudy/fog/rain plus night/sun controls; five sensor-failure cases.
- **Scale and split:** 7,885 front-view samples: 3,983/2,005/1,897 tr/va/te. All six views: 47,310. Views are not independent scenes.
- **References, alignment, and labels:** 25 semantic classes; instance annotations also supplied. Registered simulated modalities; HHA is a depth encoding, not an additional sensor.
- **Access and qualifications:** Author project and Google Drive release; repository Apache-2.0 is a code license, not inferred data redistribution permission. Four CLDE train/test implementations verified.

### IDD-AW

[Primary resource](https://iddaw.github.io/static/pdfs/IDDAW_WACV24_final.pdf)

- **Modalities and sampling:** VIS 400–670 nm, NIR 740–1,000 nm; two-CMOS prism camera.
- **Origin and conditions:** R; rain, fog, snow; low-light subset is a separate condition.
- **Scale and split:** 5,000 pairs from 202 sequences: 1,500 rain, 1,500 fog, 1,000 snow, 1,000 low-light. Sequence-exclusive train/test; exact frame split NR.
- **References, alignment, and labels:** Synchronized, timestamp-matched pairs manually checked; 30 finest-level semantic classes in a four-level hierarchy. No clean counterpart.
- **Access and qualifications:** Official IDD portal requires login; data license NR. NIR is not TIR. Website licensing must not be substituted for dataset terms.

### RASMD

[Primary resource](https://doi.org/10.1016/j.inffus.2025.103872)

- **Modalities and sampling:** VIS 2,048×1,536, SWIR 1,296×1,032; SWIR 1,000–1,700 nm.
- **Origin and conditions:** R; sunny, cloudy, rainy, snowy: respectively 43,200 / 33,400 / 10,700 / 12,700 pairs in the reported version.
- **Scale and split:** 100,000 pairs. Detection v1: 1,432 train / 956 test images per modality; merged test 780. New detection V2 counts NR.
- **References, alignment, and labels:** Software-triggered, calibrated homography/crop; residual depth-dependent parallax. Six detection classes with separate and merged labels; no clean target.
- **Access and qualifications:** Author Hugging Face release is gated; CC BY-NC-SA 4.0 dataset card. Aligned and unregistered data are distinct products. SWIR is not TIR; freeze the detection release.

### MS^2

[Primary resource](https://sites.google.com/view/multi-spectral-stereo-dataset)

- **Modalities and sampling:** Stereo VIS, NIR, TIR, LiDAR; GNSS/IMU. Cameras 15 Hz, LiDAR 10 Hz.
- **Origin and conditions:** R; verified rainy subset and clear day/night controls. Released fog/snow strata NR.
- **Scale and split:** 24 raw sequences. Depth subset: 26K train / 4K validation; 5.8K day / 6.8K night / 5.2K rain test pairs.
- **References, alignment, and labels:** Calibration and synchronization provided; cross-camera reprojection required. Filtered LiDAR depth and odometry; no clean fusion target. Split by sequence, location and condition.
- **Access and qualifications:** Author request form and public loader; CC BY-NC-SA 3.0. Multi-band stereo and thermal depth resource; depth labels do not establish image-semantic supervision.

### SHIFT

[Primary resource](https://arxiv.org/abs/2206.08367)

- **Modalities and sampling:** Multi-view/stereo VIS 1,280×800, 128-beam LiDAR, GNSS/IMU; rendered depth/flow labels.
- **Origin and conditions:** S; CARLA discrete and continuous changes of rain, fog, cloud, illumination and severity.
- **Scale and split:** 2.5M annotated frames. Paper table and component counts imply 4,850 sequences, while prose states 5,250; freeze the downloaded manifest. Train/validation/test groups provided.
- **References, alignment, and labels:** Synchronized acquisition; semantic/instance labels, depth/flow and 2D/3D boxes. Same-pose clear-weather reference protocol NR.
- **Access and qualifications:** Public download scripts and loaders. Code MIT; separate dataset license NR. Frame, sequence, image and video sampling units must be kept distinct.

### SEVD

[Primary resource](https://eventbasedvision.github.io/SEVD/)

- **Modalities and sampling:** VIS and simulated events; rendered semantic, instance, depth and flow labels. Six ego views.
- **Origin and conditions:** S; CARLA rain/fog with clear, cloudy, wet and illumination controls.
- **Scale and split:** 27 h fixed-view and 31 h ego streams; approximately 9M 2D/3D boxes. Paper split 70/15/15%; detection experiments use a smaller subset.
- **References, alignment, and labels:** Co-rendered per-view labels; depth and flow products are label renderers, not independently measured sensors. No verified clean-weather counterpart protocol.
- **Access and qualifications:** Author request form and public repository; data license NR. Reported 162/186 modality-hours sum six modalities and must not replace 27/31 independent recording hours.

### Adver-City

[Primary resource](https://labs.cs.queensu.ca/quarrg/datasets/adver-city/)

- **Modalities and sampling:** VIS, 32-beam LiDAR, GNSS/IMU; four RGB and four semantic renderers per platform.
- **Origin and conditions:** S; CARLA and OpenCDA soft/heavy rain, fog, combined fog/rain; clear and glare controls.
- **Scale and split:** 24,087 frames, 890,127 annotations, 110 scenarios; five viewpoints. Exact train/validation/test manifest NR.
- **References, alignment, and labels:** Semantic views and six-category object boxes; synchronized cooperative viewpoints. Group scenarios when splitting; viewpoints are not independent scenes.
- **Access and qualifications:** Official FRDR dataset link and public generation code; data terms NR, code MIT. Repository/portal presence was verified; large archive contents were not downloaded.

### MSU-4S

[Primary resource](https://www.egr.msu.edu/waves/msu4s/)

- **Modalities and sampling:** Three RGB cameras 2,048×1,536, 64-/32-beam LiDAR, six radars, GNSS/IMU.
- **Origin and conditions:** R; rain/snow and clear conditions across four seasons.
- **Scale and split:** Release v1.2.2 lists nine dated segments; synchronized frame total and fixed learning split NR.
- **References, alignment, and labels:** Timestamp synchronization and frame transforms; 3D boxes/tracks and weather tags on subsets. Dense image-semantic labels NR.
- **Access and qualifications:** Official mirrors/downloader; noncommercial Creative Commons terms stated, exact variant NR. FLIR Blackfly cameras are RGB, not TIR. Release errata identify LiDAR artifacts and missing radar channels.

### Ithaca365

[Primary resource](https://arxiv.org/abs/2208.01166)

- **Modalities and sampling:** Four RCCB cameras 1,928×1,208, three LiDARs, GPS/INS.
- **Origin and conditions:** R; repeated route under rain/snow, sun/cloud and night.
- **Scale and split:** >680K frames, 40 traversals of a 15 km route. Paper describes 7K selected amodal masks; current mask-release count NR.
- **References, alignment, and labels:** Calibrated streams; 3D boxes, image amodal-road/instance masks and depth. Geographic/day splits differ by task. Different-day observations are not pixel-aligned clean targets.
- **Access and qualifications:** Public author devkit and amodal-road code; data license NR. Binary amodal-road semantics support image-semantic evaluation but are not interchangeable with multiclass visible-scene labels.

### MuFoRa

[Primary resource](https://doi.org/10.1007/s42979-026-04976-9)

- **Modalities and sampling:** Stereo VIS and two solid-state LiDARs; synchronized VGA cameras at 10 Hz.
- **Origin and conditions:** R, controlled chamber; fog visibility 5–160 m and rain 20–100 mm/h; targets at 5–50 m.
- **Scale and split:** Verified protocol: 50 rain sequences and 10 fog-dissipation sequences; full file total and learning split NR. Zenodo v5.
- **References, alignment, and labels:** Known target distances and calibration objects; clear baseline observations, day-specific extrinsics. No verified image-semantic annotations.
- **Access and qualifications:** Zenodo metadata public; files restricted by request. Dataset license NR. Article open-access terms do not establish data terms; controlled physical weather is not simulated image corruption.

### FIReStereo

[Primary resource](https://doi.org/10.1109/LRA.2025.3536278)

- **Modalities and sampling:** Stereo TIR, LiDAR and IMU; 16-bit thermal except 8-bit Firesgl subset.
- **Origin and conditions:** R; rainy-night Frick and cloudy-day Hawkins; smoke/fire subsets are separate visibility conditions.
- **Scale and split:** Project reports 204,594 ``stereo thermal images''; pair/image unit unresolved. 35,706 smokeless images with depth-map pairs; 16 trajectories at four locations.
- **References, alignment, and labels:** Calibrated thermal stereo; multi-scan LiDAR depth with occlusion filtering. Training/test intentions vary by location; exact frame split NR. No semantic GT verified.
- **Access and qualifications:** Author request survey and download script; data license NR. No VIS camera is credited from later secondary descriptions; smoke must not be relabeled as fog.

### Pixel-Accurate Depth Benchmark

[Primary resource](https://arxiv.org/abs/1906.08953)

- **Modalities and sampling:** Stereo VIS 1,920×1,024 and 905 nm HDL-64 S3 LiDAR; PPS synchronization.
- **Origin and conditions:** R, controlled chamber; 17 fog visibility levels (20–100 m), two rain levels, clear/day/night controls.
- **Scale and split:** 1,600 samples in four static road scenarios; evaluation benchmark, not a verified train/test learning split.
- **References, alignment, and labels:** High-resolution geodesic depth reference measured in clear conditions; calibrated sensor projections. No verified semantic labels or ideal fused image.
- **Access and qualifications:** Registration through DENSE portal; public MIT evaluation code, data license NR. Distinct measurement protocol within the DENSE family; assess overlap before combining with Seeing Through Fog.

### nuScenes

[Primary resource](https://www.nuscenes.org/)

- **Modalities and sampling:** Six VIS cameras, one LiDAR, five radars, GNSS/IMU.
- **Origin and conditions:** R; broad driving conditions including rain/night; exact weather-subset counts NR.
- **Scale and split:** 1,000 scenes of 20 s; 1.4M images and 390K LiDAR sweeps. Official train/validation/test releases; split counts NR.
- **References, alignment, and labels:** Calibrated timestamped streams, 3D boxes; later lidarseg/panoptic releases annotate points. No camera-image semantic GT verified for a common image-semantic task.
- **Access and qualifications:** Official portal and devkit; current data license not re-audited. Context for weather-relevant multisensor detection; point-semantic labels do not certify a common image-semantic evaluation.

## Remote sensing and spatial–spectral fusion

### SEN12MS-CR

[Primary resource](https://mediatum.ub.tum.de/1554803)

- **Modalities and sampling:** S1 VV/VH SAR; cloudy/clear S2, 13 bands; 256^2 patches.
- **Origin and conditions:** R; thin haze to dense clouds, four seasons.
- **Scale and split:** 122,218 triplets; current author page: 175 ROIs. ROI-level official split.
- **References, alignment, and labels:** Geographic co-registration and band resampling; other-date clear S2; masks/land-cover links.
- **Access and qualifications:** TUM release, about 272 GB, author loader; CC BY 4.0. Older counts must remain version-specific.

### SEN12MS-CR-TS

[Primary resource](https://patricktum.github.io/cloud_removal/sen12mscrts/)

- **Modalities and sampling:** S1 VV/VH SAR + 13-band S2.
- **Origin and conditions:** R; year-round cloud variation.
- **Scale and split:** 15,578 patch time series; 53 ROIs, 30 dates, two sensors. Geographic tr/te.
- **References, alignment, and labels:** Co-registered but not fully simultaneous; timestamps, cloud masks, selected clear references.
- **Access and qualifications:** TUM and author toolbox. Training release CC BY 4.0 verified; test-page license unverified here. Related to D20.

### AllClear

[Primary resource](https://allclear.cs.cornell.edu/)

- **Modalities and sampling:** S1 SAR, S2 MS, Landsat-8/9 MS.
- **Origin and conditions:** R; clouds and shadows across 2022.
- **Scale and split:** 23,742 ROIs; 4,354,652 images. Datasheet instances: 278,613 tr / 14,215 va / 55,317 benchmark.
- **References, alignment, and labels:** Common geographic grid/resampling; masks, land cover, metadata. Temporal targets may retain contamination.
- **Access and qualifications:** Author project/code; CC BY-NC 4.0. Images and sequence instances are different units; valid-target masking required.

### M3R-CR

[Primary resource](https://github.com/zhu-xlab/M3R-CR)

- **Modalities and sampling:** Planet MS at 3 m; S1 SAR/WorldCover at 10 m.
- **Origin and conditions:** R; clouds, four seasons.
- **Scale and split:** 63,000 quartets: 60K tr / 3K te; 660 / 120 AOIs. Optical 300^2; SAR/labels 90^2.
- **References, alignment, and labels:** Orthorectified, geographically registered; other-date optical targets; six remapped land-cover classes.
- **Access and qualifications:** Author repository; data/Planet rights NR. Resampled SAR does not supply native 3 m detail.

### AIR-POLSAR-CR1.0

[Primary resource](https://www.mdpi.com/2072-4292/17/2/275)

- **Modalities and sampling:** RGB+NIR and C-band full-polarimetric SAR features; 0.5 m, 256^2.
- **Origin and conditions:** R airborne base + S cloud masks; five coverage ranges.
- **Scale and split:** 2,030 aligned patch groups. Split NR.
- **References, alignment, and labels:** Pre-mask optical references; registration, mosaicking, and resampling. Seven dominant scene labels, not pixel classes.
- **Access and qualifications:** Original data statement; download availability/license NR. Mask occlusion differs from cloud radiative transfer.

### CloudSEN12 legacy

[Primary resource](https://cloudsen12.github.io/Legacy/)

- **Modalities and sampling:** S2 L1C/L2A, S1 SAR, terrain/land-cover auxiliaries.
- **Origin and conditions:** R; thin/thick clouds and shadows.
- **Scale and split:** Original paper: 49,400 in abstract/methods, 49,250 in summary. Version-specific ROIs/splits.
- **References, alignment, and labels:** Geographic time-series alignment; dense/scribble/unlabeled groups. Not standard paired reconstruction GT.
- **Access and qualifications:** Author site/Science Data Bank. BY-NC-SA 4.0 versus BY-NC 4.0 discrepancy unresolved. Primarily cloud labeling.

### RICE-I / II

[Primary resource](https://arxiv.org/html/1901.00600)

- **Modalities and sampling:** Three-channel optical; mask for II; 512^2.
- **Origin and conditions:** I: Google Earth cloud-layer switching. II: R LandsatLook.
- **Scale and split:** I: 500 pairs. II: 450 cloudy/clear/mask groups. Fixed split NR.
- **References, alignment, and labels:** I display-layer reference; II other-date clear image within 15 days. Registration/time changes require checking.
- **Access and qualifications:** Author repository/cloud drive; license NR. No SAR; not full-band Landsat or TIR.

### PanTCR-GF2

[Primary resource](https://github.com/dusongcheng/PanTCR-GF2)

- **Modalities and sampling:** PAN 1 m; four-band MS 4 m. RR 128^2; FR 512^2.
- **Origin and conditions:** R; thin cloud; excludes marked land changes and selected clear/thick-cloud cases.
- **Scale and split:** 15,603 samples from 20 scene pairs: 14,065 tr / 1,438 va / 80 RR te / 20 FR te.
- **References, alignment, and labels:** Other-date references within one month; subpixel registration and histogram matching. No native 1 m MS GT.
- **Access and qualifications:** Author repository/drive; data license NR. Spatial independence of source-scene patches must be verified.

### PanCollection

[Primary resource](https://github.com/liangjiandeng/PanCollection)

- **Modalities and sampling:** PAN + MS; WV3, WV2, QuickBird, and GF2.
- **Origin and conditions:** C; real images with simulated resolution reduction, not weather.
- **Scale and split:** Sensor/release-specific counts and splits; WV3 RR test has 20 examples.
- **References, alignment, and labels:** RR uses native MS reference; FR lacks true high-resolution MS target. WV3 correspondence corrected in 2023.
- **Access and qualifications:** Author repository/drives; data terms NR. Tool GPL does not automatically license imagery.

### Houston 2013

[Primary resource](https://www.grss-ieee.org/community/technical-committees/2013-ieee-grss-data-fusion-contest/)

- **Modalities and sampling:** 144-band HS (380–1050 nm) + LiDAR DSM; 2.5 m, 349×1905.
- **Origin and conditions:** Original scene: R cloud shadows; shadow-removed variants also used.
- **Scale and split:** One scene; 2,832 tr / 12,197 te labeled pixels, 15 classes; no fixed va set.
- **References, alignment, and labels:** Land-cover reference, no paired clear HS GT. HS/LiDAR acquired June 23/22, 2012; not simultaneous.
- **Access and qualifications:** Official contest route; full unrestricted archive/terms not established by the cited source. Weather task evidence; distinguish raw and corrected HS versions.

### Chikusei

[Primary resource](https://naotoyokoya.com/Download.html)

- **Modalities and sampling:** 128-band HS; 2.5 m; 2517×2335.
- **Origin and conditions:** R, C; derived MS commonly simulated.
- **Scale and split:** One scene; no unified fusion tr/te split.
- **References, alignment, and labels:** Native HS can reference synthetic resolution tasks; 19 land-cover labels. No measured weather pair.
- **Access and qualifications:** Author ENVI/MAT download; CC BY 3.0. Split spatially; not native dual-sensor weather data.

### CAVE

[Primary resource](https://cave.cs.columbia.edu/repository/Multispectral)

- **Modalities and sampling:** 31 spectral bands, 400–700 nm at 10 nm intervals; 512^2.
- **Origin and conditions:** R laboratory captures, C; indoor objects/materials.
- **Scale and split:** 32 scenes. Unified fusion split NR.
- **References, alignment, and labels:** Calibrated band measurements; representative RGB is rendered. No weather labels/paired clean target.
- **Access and qualifications:** Columbia archive; independent license NR. Spectral measurement is not a weather-fusion sensor pair.

### SMILE-CR

[Primary resource](https://www.kaggle.com/datasets/yuxiawhu/smile-cr)

- **Modalities and sampling:** Landsat-8 six-band MS (30 m), MODIS six bands (500 m), S1 VV/VH; 512^2 common-grid patches.
- **Origin and conditions:** S cloud/shadow effects transferred onto real clear SMILE parents; coverage 0–100%.
- **Scale and split:** 1,400 multimodal groups: 1,000 tr / 200 va / 200 te. Authors call groups pairs.
- **References, alignment, and labels:** Original pre-corruption Landsat-8 reference and cloud masks; geographically aligned sensors acquired within a close time range.
- **Access and qualifications:** Author Kaggle route; archive/scene-disjoint manifest not inspected; license NR. Related to clear SMILE, not independent acquisition.

### BiSO-CR family

[Primary resource](https://www.kaggle.com/datasets/yuxiawhu/biso-cr)

- **Modalities and sampling:** BiS1L8-CR: S1 + Landsat-8; BiS1S2-CR: S1 + S2. Bi-temporal SAR–optical inputs.
- **Origin and conditions:** Large cloud cover; paper reports S and R experiments, but released subset allocation NR.
- **Scale and split:** Exact group counts, dimensions and tr/va/te split NR in inspected primary sources.
- **References, alignment, and labels:** Target optical reference; precise temporal filtering and cloud construction NR. Input timing can vary.
- **Access and qualifications:** Author Kaggle route verified; data files/terms not inspected. One family with two subsets; real-cloud subset needs verification.

### TCSEN12

[Primary resource](https://doi.org/10.5281/zenodo.19707507)

- **Modalities and sampling:** Multi-temporal S1 SAR and S2 optical; channel counts in released tensors NR.
- **Origin and conditions:** R; cloudy auxiliary optical, flooding and temporal change; Zhengzhou, July 2021.
- **Scale and split:** Zenodo v1: 7.2 GB archive. Sample/patch counts and tr/va/te split NR; size is not a sample count.
- **References, alignment, and labels:** Cloudy optical at T_1 and SAR at T_1,T_2 predict optical at T_2; inspected preprint selects <5% cloud targets, with six-day composites.
- **Access and qualifications:** Actual Zenodo file listing verified; access conditions require checking; license NR. Temporal generation, not simultaneous clean/degraded pairing.

### ZY1-02D HS–MS–PAN

[Primary resource](https://doi.org/10.48550/arXiv.2407.02387)

- **Modalities and sampling:** HS: 76 selected bands, 30 m; MS: eight bands, 10 m; PAN: 2.5 m.
- **Origin and conditions:** R sensor acquisition, C; no verified weather labels or weather-pair protocol.
- **Scale and split:** One tri-modal scene: HS 2071×2033, MS 6213×6099, PAN 24852×24396. Unified split NR.
- **References, alignment, and labels:** Measured co-registered modalities; no full-resolution HR-HS GT. Native HS can reference resolution-reduction experiments.
- **Access and qualifications:** Author repository links Baidu/Kaggle/AI Studio; archive not inspected; data license NR. Crops are not independent scenes; data report is a 2024 preprint.
