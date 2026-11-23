# LabelImg Setup (Python 3.12 Workaround)

## Problem

LabelImg 1.8.6 is not fully compatible with Python 3.12 because it still imports:

```python
import distutils.spawn
```

However, `distutils` was removed from Python 3.12.

Typical error:

```text
ModuleNotFoundError: No module named 'distutils'
```

---

## Environment

Project:

```text
07-24_labeling
├── .venv
├── data
│   └── images
│       ├── classes.txt
│       ├── image1.png
│       ├── image2.png
│       └── ...
```

Python:

```text
Python 3.12
```

LabelImg:

```text
1.8.6
```

---

## Solution

Copy the `distutils` package from an older Python installation.

Source:

```text
C:\Users\LB6306\AppData\Local\Programs\Python\Python39\Lib\distutils
```

Destination:

```text
<project>\.venv\Lib\site-packages\distutils
```

Result:

```text
.venv
└── Lib
    └── site-packages
        ├── distutils
        ├── labelImg
        ├── PyQt5
        └── ...
```

After copying, LabelImg starts normally.

---

## Install

Create venv:

```bash
python -m venv .venv
```

Activate:

```bash
source .venv/Scripts/activate
```

Install LabelImg:

```bash
pip install labelImg
```

Copy:

```text
Python39\Lib\distutils
```

to:

```text
.venv\Lib\site-packages\distutils
```

---

## Start LabelImg

Open the project folder and activate the venv.

Launch LabelImg with images and YOLO classes file:

```bash
labelImg data/images data/images/classes.txt
```

Arguments:

```text
data/images              -> image directory
data/images/classes.txt  -> YOLO class list
```

---

## Verify

If successful, LabelImg opens and automatically loads:

```text
data/images
```

and

```text
data/images/classes.txt
```

ready for YOLO annotation.

---

## Notes

This workaround is required only because LabelImg 1.8.6 still depends on `distutils`.

If the virtual environment is recreated, the `distutils` folder must be copied again.