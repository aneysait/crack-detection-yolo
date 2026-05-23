# crack-detection-yolo

YOLOv8 pipeline for detecting structural cracks and surface defects in concrete, trained on public data. A clean, reproducible companion to my published work on ML-based crack detection.

> Background: I developed and deployed a crack-detection pipeline on drone-captured imagery during an R&D internship, and published on it (IEEE Xplore, first author; *Automation in Construction*, co-author). This repo reimplements the core approach on an **open dataset** so it's fully shareable and reproducible.

<!-- TODO: drop a detection sample image here -->
<!-- ![sample detection](docs/sample.png) -->

## What it does

- Detects and localizes cracks / defects in concrete surface images
- Runs inference on single images, folders, or video
- Exports annotated outputs + a structured detection log (class, confidence, bbox)

## Dataset

Trained on a public concrete-crack dataset.
<!-- TODO: name the exact dataset + link, e.g. SDNET2018 / Concrete Crack Images -->

## Stack

`Python 3.10+` · `ultralytics` (YOLOv8) · `OpenCV` · `PyTorch`

## Quickstart

```bash
pip install -r requirements.txt

# inference on a folder of images
python infer.py --weights weights/best.pt --source data/test_images --save

# train from scratch on the public dataset
python train.py --data configs/crack.yaml --epochs 100 --imgsz 640
```

## Results

| Metric | Value |
|---|---|
| mAP@50 | _TODO_ |
| Precision | _TODO_ |
| Recall | _TODO_ |

## Roadmap

- [ ] Depth estimation for crack severity
- [ ] Deploy perception loop onto a mobile robot (Unitree Go2 / DimOS)

## License

MIT
