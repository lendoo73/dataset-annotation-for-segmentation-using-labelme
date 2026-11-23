# LabelMe to YOLO Annotation Converter

## Usage

```bash
python labelme2yolo.py --dataset coffee-leaf-dataset/images --names coffee-leaf-dataset/classes.txt
```

## Purpose

This script converts annotations created with **LabelMe** into a format that is compatible with **YOLO segmentation models**.

The script:

- Reads all LabelMe JSON annotation files from the specified dataset folder.
- Uses the class names defined in `classes.txt`.
- Converts annotated object polygons into YOLO segmentation format.
- Copies the corresponding image files into the output folder.
- Creates a `yolo_annotation` folder containing the converted annotations and associated images.

After execution, the generated dataset can be used for training YOLO segmentation models.

## Output

```text
coffee-leaf-dataset/images/
└── yolo_annotation/
    ├── image1.jpg
    ├── image1.txt
    ├── image2.jpg
    ├── image2.txt
    └── ...
```