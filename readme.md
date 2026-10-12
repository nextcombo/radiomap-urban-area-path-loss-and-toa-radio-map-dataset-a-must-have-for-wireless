# [RadioMap] Urban Area Path Loss and ToA Radio Map Dataset | A Must-Have for Wireless Positioning Deep Learning Research | [Includes Python Code]

📸 Urban Area Path Loss and ToA Radio Map Dataset | A Must-Have for Wireless Positioning Deep Learning Research
The dataset is generated based on real city maps, and it also includes two core radio map data: path loss / received signal strength RSS and signal arrival time ToA.
Two major applications of the dataset:✅ Supports deep learning city map path loss prediction and ray tracing simulation research✅ Provides standard test benchmark for wireless positioning algorithms
Since the RSS and ToA maps are based on the same simulation environment and the same city map, they can achieve a fair comparison of two types of positioning algorithms.
The entire dataset is simulated using professional ray tracing software, with a spatial resolution of up to 1 meter. It fills the current academic gap in the absence of similar public datasets and can provide core data support for wireless communication, geometric deep learning, and high-precision outdoor positioning fields.
🔍 II. Research Introduction Radio maps are standardized representations of key channel parameters under fine spatial grids in wireless communication, with path loss being the most core metric.
It is used to quantify the wireless signal attenuation between the transmitter Tx and the receiver Rx due to large-scale effects such as free space propagation, building/vehicle shadowing, reflection, diffraction, etc., often calculated in dB units.
💡 The widespread application of path loss maps in D2D device direct link scheduling
Terminals and cellular base stations intelligent association
Wireless positioning based on fingerprint
Physical layer security, large-scale MIMO power control
MIMO-NOMA user pairing, path planning, pedestrian activity detection
Currently, there is no publicly available dataset that includes both RSS path loss and ToA arrival time for city-level high-precision radio maps.
This study utilizes the commercial simulation software WinProp for ray tracing simulations. This tool has been validated in multiple cities such as Munich, Berlin, Hong Kong, and Helsinki through field measurements, and is widely adopted by mainstream operators.
The current simulation generates a dataset with a resolution of 1 meter, suitable for high-precision positioning algorithm research; relying on field measurements to build an equivalent accuracy map would be extremely costly and challenging.
The dual-dimensional data within a unified simulation environment perfectly supports fair comparisons between RSS and ToA positioning methods, possessing immense practical value for the entire communication and machine learning research community.
🛠️ III. Methodology and Core Theories:
1. Overall Simulation Preparation: The city data source is derived from OpenStreetMap, covering six cities including Ankara, Berlin, London, and a total of 701 standard city maps measuring 256×256 meters.
📡 Each map is equipped with 80 transmitters, resulting in a total of 56,080 simulations; divided into two scenarios:
- Ground layer: Tx at a height of 1.5m, suitable for D2D communication, 2D plane simulation
- Roof layer: Tx mounted on building roofs, suitable for cellular base station, 3D stereo simulation
🔬 Two types of simulation propagation models:
1. Dominant Path Model (DPM)
2. Intelligent Ray Tracing (IRT): Supports 2x/4x Ray Environment Interactions (IRT2 / IRT4), adjustable building tile sizes to control simulation precision
📊 Data specifications:
- Resolution: 1 meter / pixel, saved as PNG format
- Building outlines, roads, and transmitter coordinates provided in JSON polygon files
- Path loss is clipped to its extreme values, mapped to a grayscale image ranging from 0 to 255, with high path gain corresponding to highlighted pixels
2. 2D Dataset System: 2D scenario: ground transmitters at a height of 1.5m, uniform building height of 25m, carrier frequency of 5.9GHz, bandwidth of 10MHz.
🚗 Includes vehicle interference versions, each map is randomly placed with 100 simulated vehicles distributed along the road in random directions; through "with/without" simulation difference weighting, it precisely quantifies the impact of vehicle obstruction on signal propagation.
📚 The RadioMapSeer basic dataset is based on DPM, IRT2, and IRT4 full-dimensional simulations; additionally provides distorted maps with 1 to 4 buildings randomly removed, adapting to algorithm robustness tests under unreliable urban map conditions, and adapting to training for deep learning radio map prediction models like RadioUNet.
🔎 High precision fine 2D dataset reduces building tiles from 100m to 10m, restoring more delicate signal reflection and shadow changes, meeting the research needs of high-sensitive communication scenarios.
📍 Two dedicated datasets for positioning:
RadioLocSeer: Targeted at RSS path loss fingerprint positioning, includes RadioUNet predicted maps, divides training / test sets, used for performance evaluation of positioning algorithms.
RadioToASeer: Extracts dominant path ToA time-series information, exclusively for ToA ranging-based positioning algorithms, achieving a fair benchmark against RSS positioning.
3.3D stereo dataset RadioMap3DSeer: Building height range: 6.6~19.8m, representing realistic city terrain with varying heights.
Transmitters are mounted on rooftops of buildings above 5 floors, 3m above the rooftop.
Carriers at 3.5GHz, bandwidth 20MHz, typical cellular communication frequency band.
Using IRT2 simulation, 10m fine tiled data; building height coded as grayscale image, also providing black and white building masks.
Innovate by vertically splitting 3D buildings into 12 horizontal slices, inputting an improved version of RadioUNet: Predicted RMSE reduced from 1.26dB to 0.87dB, accurately learning the impact patterns of building height on signal shadow and path loss.
4. Positioning algorithm comparison: core conclusions - dense urban areas with NLOS (Non-Line of Sight) effects are severe, traditional TOA (Time of Arrival) ranging errors are significant, and radio map fingerprint positioning has a distinct advantage in anti-interference.
The self-developed deep learning model LocUNet outperforms traditional TOA ranging algorithms such as POCS, SDP, and Robust SDP.
The TOA dataset is generated based on the shortest dominant path, and the test results can serve as the theoretical upper limit for real-scene algorithm performance.
5. Threshold calculation theory combined with noise power spectral density, noise figure, and transmitting power to derive the noise floor, calculating the threshold for path loss detection; additional set of analytical cutoff thresholds are set to accommodate multi-task research scenarios such as positioning and coverage classification.
✅ 4. Research conclusions:
This study releases the world's first open-source radio map dataset that simultaneously includes RSS path loss + TOA arrival time for dense urban areas, covering 2D D2D and 3D base station scenarios, with 701 real city maps at 1-meter high resolution, filling the data gap in the field.
2
The dataset is adapted to three major research directions:👉 Deep learning for rapid prediction of radio maps👉 Fair comparison between RSS and TOA wireless positioning algorithms👉 Modeling of channel propagation characteristics in 3D urban environments.
3
The dataset supports MLSP 2023 positioning competition and ICASSP 2023 signal processing challenge, significantly promoting algorithm iteration and academic exchange in the field.
4
Simulation accuracy verified by commercial software plus multi-city field measurements, including vehicle obstruction, missing buildings, variable building heights, suitable for research on algorithm generalization and robustness.
5
Based on the dataset, the advantages of LocUNet, 3D enhanced RadioUNet, and other deep learning solutions have been validated. In urban non-line-of-sight scenarios, the positioning accuracy and channel prediction accuracy comprehensively surpass traditional convex optimization and TOA ranging methods, providing a standard data benchmark for 6G network construction, outdoor high-precision positioning, and intelligent cellular network research.

## Images

![(RadioMap)Dense Urban Area Path Loss and ToA Radio Map Dataset | A Must-Have for Wireless Positioning Deep Learning Research | [Includes Python Code]](01.jpg)
![(RadioMap)Dense Urban Area Path Loss and ToA Radio Map Dataset | A Must-Have for Wireless Positioning Deep Learning Research | [Includes Python Code]](02.jpg)
![(RadioMap)Dense Urban Area Path Loss and ToA Radio Map Dataset | A Must-Have for Wireless Positioning Deep Learning Research | [Includes Python Code]](03.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
