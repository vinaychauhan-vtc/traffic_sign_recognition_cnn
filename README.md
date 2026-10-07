# Traffic Sign Recognition using CNN

A ready-to-run Deep Learning project for the German Traffic Sign Recognition Benchmark (GTSRB), built with PyTorch.

## Features
- CNN classification for 43 traffic-sign classes
- GTSRB class-folder dataset loader
- Data augmentation
- Train/validation split
- Accuracy and classification report
- Single-image prediction
- Best-model checkpoint
- CPU/GPU support

## Structure
```text
traffic_sign_recognition_cnn/
├── src/
│   ├── train.py
│   ├── evaluate.py
│   ├── predict.py
│   ├── model.py
│   ├── dataset.py
│   ├── utils.py
│   └── class_names.json
├── models/
├── data/
├── requirements.txt
└── README.md
```

## Install
```bash
python -m venv venv
```
Windows:
```bash
venv\Scripts\activate
```
Linux/macOS:
```bash
source venv/bin/activate
```
Then:
```bash
pip install -r requirements.txt
```

## Dataset
Download the GTSRB dataset separately. Put its `Training` folder here:

```text
data/GTSRB/GTSRB/Training/
├── 00000/
├── 00001/
...
└── 00042/
```

Or provide any Training-folder path with `--data_dir`.

## Train
```bash
python src/train.py --data_dir data/GTSRB/GTSRB/Training --epochs 20 --batch_size 64
```

Best model:
```text
models/traffic_sign_cnn.pth
```

## Evaluate
```bash
python src/evaluate.py --data_dir data/GTSRB/GTSRB/Training --model models/traffic_sign_cnn.pth
```

## Predict one image
```bash
python src/predict.py --image path/to/sign.jpg --model models/traffic_sign_cnn.pth
```

Example:
```text
Predicted class: 14
Confidence: 98.42%
```

## Important
The GTSRB dataset and trained weights are not included in this ZIP because the dataset is large and should be obtained separately.

The project is designed as a solid academic/college project baseline. For production-grade recognition, consider transfer learning with ResNet/EfficientNet and a carefully curated test set.
