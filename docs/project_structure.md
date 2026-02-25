# CellVision — Project Structure

```
cellvision/
├── README.md                    # Project overview, results, quick start
├── requirements.txt             # Python dependencies
├── setup.py                     # Package install
├── .gitignore
├── .env.example                 # Environment variable template
│
├── configs/                     # YAML configs (hyperparams, paths)
│   ├── classifier.yaml
│   ├── segmentation.yaml
│   └── inference.yaml
│
├── src/                         # Core library (importable package)
│   ├── data/                    # Data loading & preprocessing
│   │   ├── dataset.py           # CellMicroscopyDataset (PyTorch Dataset)
│   │   ├── synthetic.py         # Synthetic microscopy generator
│   │   ├── transforms.py        # Custom microscopy transforms
│   │   └── loaders.py           # DataLoader factory
│   │
│   ├── models/                  # Model architectures
│   │   ├── classifier.py        # MobileNetV3 transfer learning
│   │   ├── segmentation.py      # DeepLabV3 cell segmentation
│   │   └── losses.py            # DiceLoss, ComboLoss
│   │
│   ├── training/                # Training loops & metrics
│   │   ├── trainer.py           # Generic Trainer class
│   │   ├── metrics.py           # Dice, IoU
│   │   └── optimizer.py         # Optimizer/scheduler factory
│   │
│   ├── visualization/           # Plotting & TorchVision overlays
│   │   └── visualize.py
│   │
│   └── utils/                   # I/O, logging, helpers
│       ├── io.py
│       └── logging.py
│
├── scripts/                     # CLI entry points (run from project root)
│   ├── train_classifier.py
│   ├── train_segmentation.py
│   ├── predict.py
│   └── export_onnx.py
│
├── notebooks/                   # Exploration & demos (Jupyter)
│   ├── 01_data_exploration.ipynb
│   ├── 02_train_classifier.ipynb
│   ├── 03_train_segmentation.ipynb
│   └── 04_visualization.ipynb
│
├── tests/                       # Unit tests (pytest)
│   ├── test_data.py
│   └── test_models.py
│
├── data/                        # (gitignored — add your data here)
│   ├── raw/                     # Original images / annotations
│   └── processed/               # Preprocessed tensors, splits
│
├── models/                      # (gitignored)
│   ├── checkpoints/             # .pth files from training
│   └── exported/                # ONNX / TorchScript for deployment
│
├── outputs/                     # (gitignored)
│   └── figures/                 # Saved plots & visualizations
│
└── docs/
    └── project_structure.md     # This file
```
