# RadioIndustryMap

**RadioIndustryMap** is a large-scale, high-fidelity, time-varying electromagnetic (EM) / radio map dataset designed for **Electromagnetic Map Reconstruction**, **Radio Environment Mapping (REM)**, and **6G Industrial Internet of Things (IIoT)** research.

Unlike conventional radio map datasets that mainly focus on static base stations in simplified urban concrete-canyon environments, RadioIndustryMap targets realistic industrial and offshore scenarios with **mobile transmitters**, **dynamic radio propagation**, **heterogeneous material compositions**, and **complex industrial geometries**. The dataset explicitly models representative industrial materials and objects, including **metal structures, concrete buildings, vegetation, road surfaces, water surfaces, industrial facilities, containers, pipelines, storage tanks, and moving vessels**.

> **Current release status:**  
> This repository currently provides representative sample data and visualization examples for demonstration purposes. The complete RadioIndustryMap dataset will be publicly released after the corresponding paper is accepted.

This repository provides the dataset described in our paper:

> **[Paper Title Will Be Updated]**

The full paper information and dataset citation will be updated after acceptance.

---

## Citation

The citation information will be provided after the corresponding paper is accepted and published.

Please stay tuned for updates.

---

## Dataset Availability

At the current stage, this repository only releases a subset of representative examples, including sample radio maps, visualization figures, and partial metadata. These samples are intended to help users understand the data format, directory organization, and potential research tasks supported by RadioIndustryMap.

The full dataset will be released after the paper is accepted. The complete release is expected to include approximately:

| Item | Description |
|---|---|
| Number of scenes | Approximately 400 scenes |
| Number of samples | Approximately 400,000 radio map samples |
| Scenario types | Automated chemical plants, smart container ports, offshore industrial zones, moving-vessel scenarios |
| Frequency bands | 11 frequency bands |
| Receiver heights | 5 receiver heights |
| Temporal frames | 50 frames per dynamic sequence |
| Time interval | 2 seconds |
| Grid size | 512 × 512 |
| Spatial resolution | 3 m per grid cell |
| Physical coverage | 1536 m × 1536 m per radio map |

The current sample release should not be regarded as the final benchmark version. The final dataset, benchmark splits, and detailed metadata will be updated together with the full release.

---

## Why Do We Need RadioIndustryMap?

Most existing EM map and radio map datasets are built upon simplified assumptions, such as **static transmitters**, **homogeneous building materials**, and relatively regular urban layouts. These assumptions are useful for early-stage algorithm development, but they are insufficient for modeling the radio propagation characteristics of real industrial environments.

In practical wireless systems, especially in **smart factories**, **automated container ports**, **chemical plants**, **offshore industrial zones**, **autonomous driving systems**, **UAV swarms**, and **robotic inspection networks**, the radio environment is highly dynamic and materially heterogeneous. The received signal distribution can be strongly affected by:

- Mobile transmitters mounted on vehicles, robots, vessels, or temporary communication nodes;
- Metallic objects such as containers, cranes, ship hulls, storage tanks, and pipelines;
- Heterogeneous materials, including metal, concrete, vegetation, road surfaces, and water surfaces;
- Severe multipath propagation, strong specular reflection, diffraction, and scattering;
- Dynamic blockage and time-varying shadowing caused by moving industrial objects;
- Abrupt line-of-sight / non-line-of-sight transitions in dense industrial infrastructures.

For example, stacked containers in ports can create strong canyon-like propagation effects; storage tanks and pipe galleries in chemical plants can introduce deep fading and severe shadowing; moving vessels and ship hulls in offshore scenarios can cause time-varying reflection and blockage. These effects are difficult to capture using conventional static urban datasets.

**RadioIndustryMap is designed to fill this gap.** It provides a dynamic, material-aware, and large-scale radio map benchmark for developing and evaluating learning-based radio map reconstruction algorithms in realistic industrial wireless environments.

---

## Dataset Highlights

### 1. Dynamic and Time-Varying Radio Maps

RadioIndustryMap provides **50 consecutive temporal frames** for each dynamic sequence. The transmitter trajectories are discretized with a time interval of **2 seconds**, resulting in a sampling duration of **100 seconds** for each scenario.

The dataset includes both fixed and mobile transmitters. Mobile transmitters are used to emulate practical industrial communication sources, such as:

- Automated guided vehicles;
- Port delivery vehicles;
- Robotic inspection platforms;
- Mobile emergency communication nodes;
- Moving vessels and ship-mounted communication equipment.

This design enables research on:

- 4D radio map reconstruction;
- Dynamic radio environment prediction;
- Mobility-aware coverage estimation;
- Communication dead-zone prediction;
- Proactive handover and resource allocation;
- Active interference mitigation in industrial networks.

---

### 2. Realistic Industrial and Offshore Scenarios

RadioIndustryMap covers representative industrial and offshore environments, including:

- Automated chemical plants;
- Smart container ports;
- Offshore industrial zones;
- Moving-vessel scenarios;
- Large-scale industrial factory areas.

These environments are much more complex than regular urban blocks. They contain irregular industrial layouts, dense metallic facilities, large open spaces, water surfaces, vegetation regions, road networks, and moving objects. As a result, the dataset can better represent the propagation characteristics of practical 6G IIoT systems.

---

### 3. Material-Aware Electromagnetic Modeling

RadioIndustryMap explicitly considers heterogeneous material compositions. The dataset contains semantic and material information for different environmental elements, including:

- **Metal:** containers, cranes, ship hulls, pipelines, storage tanks, and industrial equipment;
- **Concrete:** buildings, workshops, warehouses, and factory structures;
- **Vegetation:** trees, green belts, and vegetation-covered regions;
- **Water surfaces:** offshore areas, port-side waters, and maritime propagation environments;
- **Road and ground surfaces:** industrial roads, factory lanes, and port operation areas.

This material-aware design enables the dataset to capture strong metal-induced reflection, shielding effects, vegetation attenuation, and maritime reflection, which are essential for realistic industrial radio map modeling.

---

### 4. Multi-Frequency and Multi-Height Coverage

RadioIndustryMap supports multiple frequency bands and receiver heights. This enables the study of frequency-dependent and height-dependent propagation characteristics.

The complete dataset will include the following frequency bands:

```text
500 MHz, 700 MHz, 900 MHz, 1500 MHz, 1800 MHz, 2000 MHz,
2100 MHz, 3500 MHz, 4900 MHz, 5000 MHz, 5800 MHz
```

The dataset includes five receiver heights:

```text
1.5 m, 5 m, 10 m, 20 m, 60 m
```

These receiver heights correspond to different industrial communication layers, including ground users, vehicles, elevated infrastructure, low-altitude nodes, and aerial communication platforms.

---

## Dataset Description

RadioIndustryMap is organized by **scenario type**, **frequency band**, **receiver height**, and **temporal frame**. Each radio map sample corresponds to a specific industrial scene, carrier frequency, receiver height, and time index.

For each scenario, the dataset provides:

- Raw radio map matrices in `.npy` format;
- Visualization images in `.png` format;
- Dynamic radio map animations in `.gif` format;
- Building spatial distribution information;
- Vegetation spatial distribution information;
- Material and environmental semantic information;
- Road topology and transmitter trajectory information;
- Geographic metadata and coordinate-related information.

The radio maps are generated on a `512 × 512` grid with a spatial resolution of `3 m`, corresponding to a physical coverage area of `1536 m × 1536 m`. For dynamic scenarios, the transmitter trajectory is sampled every `2 s`, and each sequence contains `50` consecutive temporal frames.

RadioIndustryMap can be used for both supervised learning and benchmark evaluation. It supports tasks such as sparse radio map reconstruction, time-varying radio map prediction, cross-frequency learning, multi-height radio map reconstruction, and physics-informed radio environment modeling.

---

## Dataset Preview

The following figures are placeholders. Please replace them with real images from the dataset before releasing the repository.

### Fig. 1. Dataset Overview

<p align="center">
  <img src="assets/radioindustrymap_overview.png" width="850">
</p>

<p align="center">
  <em>Overview of RadioIndustryMap, including realistic geographic maps, industrial simulation scenes, and generated radio maps.</em>
</p>

---

### Fig. 2. Geographic Map and Radio Map Pair

<p align="center">
  <img src="assets/map_radio_pair_example.png" width="850">
</p>

<p align="center">
  <em>Example of a geographic map and its corresponding generated radio map.</em>
</p>

---

### Fig. 3. Dynamic Radio Map Sequence

<p align="center">
  <img src="assets/dynamic_radio_map.gif" width="650">
</p>

<p align="center">
  <em>Example of a time-varying radio map sequence generated by mobile transmitters.</em>
</p>

---

### Fig. 4. Material and Environmental Layers

<p align="center">
  <img src="assets/material_layers.png" width="850">
</p>

<p align="center">
  <em>Example of environmental semantic layers, including buildings, vegetation, materials, roads, and geographic information.</em>
</p>

---

## Download

Representative sample data are currently available through the following cloud storage link:

- Baidu Netdisk: 

The full RadioIndustryMap dataset will be released after the corresponding paper is accepted.

Additional download links, such as Google Drive or OneDrive, may be provided in future releases.

---

## File Description

RadioIndustryMap contains radio map files, visualization files, dynamic animations, and global environmental metadata.

### Radio Map Matrix

```text
mapx_hm_t=y.npy
```

Raw radio map matrix data for model training and evaluation.

Example:

```text
map1_1.5m_t=1.npy
map1_1.5m_t=50.npy
```

where:

- `mapx` denotes the scenario or map index;
- `hm` denotes the receiver height;
- `t=y` denotes the temporal frame index.

---

### Radio Map Visualization

```text
mapx_hm_t=y.png
```

Visualization image of the corresponding radio map.

Example:

```text
map1_1.5m_t=1.png
map1_1.5m_t=50.png
```

---

### Dynamic Radio Map Animation

```text
mapx_hm.gif
```

Animated visualization of a continuous time-varying radio map sequence.

Example:

```text
map1_1.5m.gif
```

---

### Building Information

```text
Building.zip
```

This compressed file contains building spatial distribution information for the corresponding scenes.

---

### Vegetation Information

```text
vegetation.zip
```

This compressed file contains vegetation spatial distribution information.

---

### Road and Trajectory Information

```text
way.zip
```

This compressed file contains road topology and transmitter trajectory-related information.

---

### Material Information

```text
Material/
```

This directory contains material distribution maps and material labels for industrial objects.

---

### Geographic Information

```text
Geography/
```

This directory contains geographic information, including OpenStreetMap data and longitude-latitude mapping files.

---

## Directory Structure

The dataset is organized as follows:

```text
RadioIndustryMap/
├── Automated_Chemical_Plant/
│   ├── 500MHz/
│   │   ├── 1.5m/
│   │   │   ├── npy/
│   │   │   │   ├── map1_1.5m_t=1.npy
│   │   │   │   ├── map1_1.5m_t=2.npy
│   │   │   │   ├── ...
│   │   │   │   └── map1_1.5m_t=50.npy
│   │   │   ├── png/
│   │   │   │   ├── map1_1.5m_t=1.png
│   │   │   │   ├── map1_1.5m_t=2.png
│   │   │   │   ├── ...
│   │   │   │   └── map1_1.5m_t=50.png
│   │   │   └── gif/
│   │   │       ├── map1_1.5m.gif
│   │   │       └── ...
│   │   ├── 5m/
│   │   │   └── ...
│   │   ├── 10m/
│   │   │   └── ...
│   │   ├── 20m/
│   │   │   └── ...
│   │   └── 60m/
│   │       └── ...
│   ├── 700MHz/
│   │   └── ...
│   ├── 900MHz/
│   │   └── ...
│   ├── 1500MHz/
│   │   └── ...
│   ├── 1800MHz/
│   │   └── ...
│   ├── 2000MHz/
│   │   └── ...
│   ├── 2100MHz/
│   │   └── ...
│   ├── 3500MHz/
│   │   └── ...
│   ├── 4900MHz/
│   │   └── ...
│   ├── 5000MHz/
│   │   └── ...
│   └── 5800MHz/
│       └── ...
│
├── Smart_Container_Port/
│   ├── 500MHz/
│   │   └── ...
│   ├── 700MHz/
│   │   └── ...
│   └── ...
│
├── Offshore_Industrial_Zone/
│   ├── 500MHz/
│   │   └── ...
│   ├── 700MHz/
│   │   └── ...
│   └── ...
│
├── Moving_Vessel/
│   ├── 500MHz/
│   │   └── ...
│   ├── 700MHz/
│   │   └── ...
│   └── ...
│
└── Global_Index/
    ├── Material/
    │   ├── map1_material.npy
    │   ├── map2_material.npy
    │   ├── ...
    │   └── material_labels.json
    │
    ├── Building/
    │   ├── map1_building.npy
    │   ├── map2_building.npy
    │   ├── ...
    │   └── Building.zip
    │
    ├── Vegetation/
    │   ├── map1_vegetation.npy
    │   ├── map2_vegetation.npy
    │   ├── ...
    │   └── vegetation.zip
    │
    ├── Trajectory/
    │   ├── map1_tx_trajectory.npy
    │   ├── map2_tx_trajectory.npy
    │   ├── ...
    │   └── trajectory_metadata.json
    │
    └── Geography/
        ├── Open_Street_Map/
        │   └── way.zip
        │
        └── longitude_and_latitude/
            ├── map1_coordinates.npy
            ├── map2_coordinates.npy
            └── ...
```

---


## Recommended Research Tasks

RadioIndustryMap can support a wide range of research tasks, including:

- Sparse radio map reconstruction;
- Electromagnetic map completion;
- Radio environment mapping;
- Dynamic radio map prediction;
- 4D radio map reconstruction;
- Multi-frequency radio map learning;
- Multi-height radio map reconstruction;
- Cross-scenario generalization;
- Industrial wireless coverage prediction;
- Communication dead-zone forecasting;
- Mobility-aware radio map prediction;
- Geometry-aware neural network design;
- Material-aware radio map reconstruction;
- Physics-informed radio environment modeling;
- 6G IIoT network planning and optimization.


---

## Notes

1. This repository currently provides representative sample data only. The full dataset will be released after the corresponding paper is accepted.

2. RadioIndustryMap is generated for academic research on radio map reconstruction, radio environment mapping, and 6G industrial wireless communication.

3. Users should carefully check the task setting before training, especially for temporal prediction, cross-frequency learning, cross-height generalization, and cross-scenario evaluation.

4. Some geographic information is derived from OpenStreetMap-related data. Please follow the corresponding OpenStreetMap data usage and attribution requirements when using such information.

5. The dataset structure may be updated in future releases. Please refer to the latest version of this repository for updated file organization and metadata descriptions.

---

## License

The license information will be updated before the public release of the full dataset.

The currently released sample data are provided for academic demonstration and preliminary research only.

---

## Contact

If you have any questions about the dataset, please open an issue in this repository or contact the project team.

Project contact information will be updated after the dataset is released.
