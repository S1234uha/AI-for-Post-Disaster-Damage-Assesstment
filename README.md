# AI-for-Post-Disaster-Damage-Assesstment: Buildings, Vehicles, and Roads

Jupyter notebooks and **folders for trained model artifacts** covering building segmentation/damage assessment, vehicle detection and damage analysis, and disaster-scene semantic segmentation. Additional disaster-video analysis notebooks are under `notebooks/other/`.

> **Repository status:** Seven distinct Jupyter notebooks (source code and markdown) are available in `notebooks/`. Two existing car-model checkpoints (`car-75e-11n.pt` and `car-damage (1).pt`) are now also available under `models/car/`, with the original root-level copies preserved. No building or road checkpoint has been uploaded. Saved notebook outputs were cleared to keep the repository smaller.

## Project layout

```text
AI-for-Post-Disaster-Damage-Assesstment/
├── models/
│   ├── building/           # Add trained building model weights here
│   ├── car/                # Two existing car checkpoints are present
│   └── road/               # Add trained road/scene segmentation weights here
├── notebooks/
│   ├── building/           # Building footprints and multi-view damage
│   ├── car/                # Car detection, classification, severity, pipeline
│   ├── road/               # RescueNet scene segmentation (not road-only)
│   └── other/              # Disaster-video ReID / VLM analysis
├── .gitignore
├── NOTEBOOK_INVENTORY.md
└── README.md
```

## Notebooks

| Area | Notebook | Purpose |
|---|---|---|
| Building | [`zanzibar_building_footprint_segmentation.ipynb`](notebooks/building/zanzibar_building_footprint_segmentation.ipynb) | Building footprint semantic segmentation, FastAI-based |
| Building | [`multiview_building_damage_analysis.ipynb`](notebooks/building/multiview_building_damage_analysis.ipynb) | MV-HarveyNET-style multi-view building damage experiments |
| Car | [`car_damage_detection_colab.ipynb`](notebooks/car/car_damage_detection_colab.ipynb) | Vehicle damage classification experiments using Kaggle data |
| Car | [`car_damage_yolo26_finetune.ipynb`](notebooks/car/car_damage_yolo26_finetune.ipynb) | YOLO26 training for light/moderate/severe damage |
| Car | [`vehicle_damage_pipeline.ipynb`](notebooks/car/vehicle_damage_pipeline.ipynb) | Combined vehicle detection, damage classification and severity pipeline |
| Road / scene | [`rescuenet_semantic_segmentation.ipynb`](notebooks/road/rescuenet_semantic_segmentation.ipynb) | RescueNet multi-class disaster-scene segmentation, **not a dedicated road-only notebook** |
| Other | [`disaster_video_reid_vlm_colab.ipynb`](notebooks/other/disaster_video_reid_vlm_colab.ipynb) | Disaster video person ReID, tracking, and VLM processing |

See [NOTEBOOK_INVENTORY.md](NOTEBOOK_INVENTORY.md) for a source-to-filename mapping and excluded uploads.

## Add model checkpoints

1. Find the model files produced by your training runs or in your Google Drive / Colab session.
2. Place building checkpoints in `models/building/`, car checkpoints in `models/car/`, and road or disaster-scene segmentation checkpoints in `models/road/`.
3. Update the absolute paths in the Colab notebooks to match the checkpoint locations **in the environment where you run them**. Merely placing the files in this repository does not automatically change the existing `/content/...` paths.
4. Record checkpoint provenance, architecture, datasets, training settings, and license/usage rights in the relevant model folder's README.

Examples of filenames referenced in the notebooks:

- `models/car/car-75e-11n.pt` — vehicle detector
- `models/car/model_mobilenetv2.keras` — damage classifier
- `models/car/car-damage.pt` — severity model (the pipeline references a Colab copy called `car-damage (1).pt`)
- `models/car/car-damage-yolo26-finetuned.pt` — output of the YOLO26 fine-tuning notebook
- `models/road/train_epoch_100.pth` — RescueNet checkpoint path referenced by the scene-segmentation notebook

The first two car `.pt` files above are included under `models/car/`. The remaining filenames are examples of checkpoints referenced by notebooks but not currently provided.

## Run a notebook

Open a notebook in Jupyter or Google Colab. Install the requirements in its setup cells and provide its own datasets and checkpoint files. Paths to datasets and weights in the notebooks typically point to Google Colab (`/content/...`) or Google Drive; adjust them before running. Different notebooks use different frameworks/versions (FastAI, TensorFlow/Keras, PyTorch, and Ultralytics), so no single environment is guaranteed to run every notebook.

Some notebooks rely on external repositories or datasets; please check those resources' licenses and download terms. These notebooks have been **organized and cleaned of saved outputs, not executed or verified end-to-end**.

## GitHub repository

Project files are published to [`S1234uha/AI-for-Post-Disaster-Damage-Assesstment`](https://github.com/S1234uha/AI-for-Post-Disaster-Damage-Assesstment). Model weights currently at repository root were also copied into `models/car/` without deleting the originals. To add additional model weights, place them under the appropriate `models/` subdirectory.

### Large model files (Git LFS)

For binary checkpoints, consider installing [Git LFS](https://git-lfs.com/) **before** adding weights. In a Git-enabled terminal, run:

```bash
git lfs install
git lfs track "models/**/*.pt" "models/**/*.pth" "models/**/*.keras" "models/**/*.h5" "models/**/*.onnx" "models/**/*.safetensors"
git add .gitattributes models/
git commit -m "Add model checkpoints with Git LFS"
git push
```

The LFS commands require Git LFS to be installed and may incur storage/bandwidth usage. GitHub's regular file size limit is 100 MiB (and its browser upload limit is 25 MiB per file). Do not commit credentials, API keys, private training data or huge datasets. Review model and dataset licenses before publishing publicly.

## Notes

- Duplicate uploads were de-duplicated; code and markdown are unchanged.
- Execution outputs and counts were removed to make notebooks GitHub-friendly. The notebooks were not re-run.
- One uploaded `.ipynb` contained placeholder text rather than notebook JSON and could not be included.
- The uploaded NDVI GeoTIFF ZIP was not added because it is unrelated to these requested model/notebook folders.
- No license is assigned to your code by this template. Add one when you have confirmed the rights to publish the material.
