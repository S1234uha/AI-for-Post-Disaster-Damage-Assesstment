# Notebook inventory and provenance

The following source uploads were converted to cleaner, GitHub-friendly `.ipynb` files. Notebook **source code and markdown are preserved**; existing saved outputs were removed and execution counts cleared. No cells were run and no model checkpoints are included.

| Uploaded file | Repository location | Notes |
|---|---|---|
| `znz-segment-buildingfootprint-20190108-alldata.ipynb` | `notebooks/building/zanzibar_building_footprint_segmentation.ipynb` | FastAI building footprints |
| `MV_HarveyNET_Transformer_With_Quality_Visibility_Diversity_Selection (2).ipynb` | `notebooks/building/multiview_building_damage_analysis.ipynb` | Multi-view building damage |
| `car-damage-detection-colab.ipynb` | `notebooks/car/car_damage_detection_colab.ipynb` | Car damage classification |
| `car_damage_yolo26_finetune (1).ipynb` | `notebooks/car/car_damage_yolo26_finetune.ipynb` | Severity fine-tuning |
| `vehicle_damage_pipeline (3).ipynb` | `notebooks/car/vehicle_damage_pipeline.ipynb` | Three-stage vehicle damage analysis |
| `last100.ipynb` | `notebooks/road/rescuenet_semantic_segmentation.ipynb` | Multi-class RescueNet scene segmentation; **not exclusively road segmentation** |
| `Disaster_GPU_ReID_VLM_Colab (1).ipynb` | `notebooks/other/disaster_video_reid_vlm_colab.ipynb` | Disaster video tracking / ReID / VLM |

## Other uploaded items

- `last100(1).ipynb`: byte-for-byte duplicate of `last100.ipynb`, omitted.
- `car_damage_yolo26_finetune (1)(1).ipynb`: byte-for-byte duplicate of `car_damage_yolo26_finetune (1).ipynb`, omitted.
- `Video_Geolocation_Pipeline_FULL.ipynb`: uploaded content is the literal text `REPLACE_WITH_USER_NOTEBOOK`, **not a valid Jupyter notebook**. Not included. Please supply the original file if you want it included.
- `Field_1_NDVI_26Oct2026.zip`: contains NDVI GeoTIFF imagery. Not included because it is not one of the requested model checkpoints or notebook code files.

## Missing model files

No model weights such as `.pt`, `.pth`, `.onnx`, `.h5`, or `.keras` were present in the supplied uploads. Place your actual checkpoints in the corresponding `models/` folder and verify notebook paths and dependencies. The notebooks refer to example output locations in Google Drive / Colab; this package does not fetch or manufacture any model weights.
