# Dataset Annotation for Segmentation Using LabelMe

This project demonstrates converting LabelMe polygon annotations to YOLO segmentation labels. It includes the coffee leaf disease dataset and converted annotations.

## Course

Part of [YOLO26 & The Legacy: 6 in 1 YOLO Masterclass 2026](https://www.udemy.com/course/yolo-masterclass-deep-learning-computer-vision-course/).

## Dataset

The included coffee leaf disease data is associated with these Kaggle datasets:

- [Coffee leaf diseases](https://www.kaggle.com/datasets/badasstechie/coffee-leaf-diseases)
- [Coffee leaf diseases YOLO](https://www.kaggle.com/datasets/stunningvisionai/coffee-leaf-diseases-yolo)

The `coffee-leaf-dataset/images` directory contains the images and LabelMe JSON annotations. Converted YOLO segmentation labels and their images are in `coffee-leaf-dataset/images/yolo_annotation`.

## Setup

Use Python 3.12 or newer, create a virtual environment, then install the project dependencies:

```bash
python -m venv .venv
```

Activate the environment (`.venv\Scripts\activate` on Windows or `source .venv/bin/activate` on macOS/Linux), then run:

```bash
python -m pip install -r requirements.txt
```

## Convert annotations

From the project root:

```bash
python labelme2yolo.py --dataset coffee-leaf-dataset/images --names coffee-leaf-dataset/classes.txt
```

The converter writes YOLO segmentation text files and copies matching images into `coffee-leaf-dataset/images/yolo_annotation`.
