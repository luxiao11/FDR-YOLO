# FDR-YOLO Dataset Splits

This repository provides the visible-light image lists and the train, validation, and test assignments used in the FDR-YOLO experiments. The manifests identify original files so readers with the source datasets can reconstruct the same image membership and split assignments.

| Experiment subset | Manifest | Train | Validation | Test | Total |
| --- | --- | ---: | ---: | ---: | ---: |
| DroneVehicle-L | [DroneVehicle-L-split.txt](DroneVehicle-L-split.txt) | 10,465 | 2,988 | 1,504 | 14,957 |
| RGBT-Tiny-L | [RGBT-Tiny-L-split.txt](RGBT-Tiny-L-split.txt) | 5,954 | 1,701 | 854 | 8,509 |

## Reconstruct the splits

1. Obtain the original DroneVehicle and RGBT-Tiny datasets from their respective providers.
2. For DroneVehicle, use the original parent folder containing the `train/`, `val/`, and `test/` directories. Keep the nesting in the source paths, such as `train/train/trainimg/00001.jpg`. For RGBT-Tiny, use the original `images/` directory containing the DJI sequence folders. Its `00` subdirectories contain the visible-light images.
3. Read the matching manifest as UTF-8. Skip comment lines beginning with `#`. The remaining lines have three tab-separated fields: `split`, `source_relative_path`, and `destination_relative_path`.
4. Resolve each source path against the original dataset root. Resolve the destination path against a separate output folder for the experiment subset. This gives the assigned split and the experiment filename. Use the corresponding original image identifier when locating annotations.

The manifests specify image membership and split assignment. The original datasets supply the images and annotations. The manifests make no claim about a uniform illumination threshold for the historical subsets.

## Citation

For reproducible citations, cite the permanent GitHub link to this README at the commit containing both manifests. Please also cite DroneVehicle and RGBT-Tiny in work that uses their original data.
