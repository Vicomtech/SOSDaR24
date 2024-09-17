# Synthetic Open Sensor Data for Rail 2024 (SOSDaR24)

## Overview

The **Synthetic Open Sensor Data for Rail 2024 (SOSDaR24)** dataset was created to fill the gap in publicly available datasets that include both obstacles on tracks and point clouds. It was generated using the [CARLA simulator](https://carla.org/) to avoid the costs and dangers of real-world railway data collection. The dataset consists of **100 scenes with 22,208 files per sensor**, featuring both **static and dynamic obstacles** such as boxes, pedestrians, and cars.

Data is annotated using the **OpenLABEL** standard, with information such as **3D rail polylines, obstacle bounding boxes, and object tags**. CARLA recordings are included to allow scene recreation and sensor configuration.

Tasks supported include:

- Obstacle detection
- Obstacle tracking
- Track detection
- Segmentation
- Domain gap analysis

## Download

The dataset can be downloaded through the following [form](https://opendatasets.vicomtech.org/di21-sosdar24/59e9a716).

## Structure

Each scene is stored in a folder named as follows: `ID_map_path_static_dynamic` where:

- **ID**: is the id of the scene,
- **map**: is the id of the map,
- **path**: is the id of the path,
- **static**: is the number of static obstacles in the scene,
- **dynamic**: is the number of dynamic obstacles in the scene.

Each folder contains:

- **OpenLABEL** file (JSON): Labels, sensor calibration, and odometry.
- **Recording** file (.log): CARLA recording of the scene.
- **Streams** folder: Subfolders with sensor stream data (camera, pandar64, tele15).

Each stream folder contain three folders one for each sensor. The format of the images is `.png`. The format of the point clouds is `.pcd`. The point cloud data is binary and they have 5 fields: `x, y, z, object_id, object_tag`. The names of the files indicates the timestamp.

Additionally, the dataset contains a folder called `info` where there are npy files with the path followed by the train during the simulations.

## Citation

The SOSDaR24 Dataset is made freely available to academic and non-academic entities for research purposes such as academic research, teaching, scientific publications, or personal experimentation. If you use our dataset, we kindly ask you to cite our paper as:

```
@article{iglesias2024enhancing,
  title = {Enhancing Safety in Railway Environments: Interpretable Track and Obstacle Detection using On-board LiDAR},
  author = {Aitor Iglesias and Jose Luis Apellaniz and Nerea Aranjuelo and Pedro Brandimarte and Jokin Irastorza and Marcos Nieto},
  journal = {IEEE Transactions on Intelligent Transportation Systems (T-ITS)},
  note = {Under review},
  year = {2024},
  specialissue = {Cyber and Digital Information in Railway Engineering and Operation}
}
```

## Acknowledgment

This work has received funding from the Basque Government under project AutoTrust of the program ELKARTEK-2023 and project THAVA of the program HAZITEK-2022.

## License

[![CC BY-NC-ND 4.0][cc-by-nc-nd-image]][cc-by-nc-nd]

All datasets on this page are copyrigh by Vicomtech and published under the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 License. This means that you must attribute the work in the manner specified by the authors, you may not use this work for commercial purposes and if you remix, transform, or build upon the material, you may not distribute the modified material.

[cc-by-nc-nd]: http://creativecommons.org/licenses/by-nc-nd/4.0/
[cc-by-nc-nd-image]: https://licensebuttons.net/l/by-nc-nd/4.0/88x31.png