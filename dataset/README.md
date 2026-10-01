---
language:
  - vi
  - en
license: cc-by-4.0
task_categories:
  - object-detection
tags:
  - traffic-sign
  - vietnam
  - yolov8
  - autonomous-vehicles
size_categories:
  - 10K<n<100K

configs:
  - config_name: default
    data_files:
      - split: train
        path: "classid.csv"
---

# Vietnam Traffic Sign Detection Dataset

[![YOLO](https://img.shields.io/badge/Model-YOLO-blueviolet?style=for-the-badge&logo=ultralytics&logoColor=white)](https://github.com/ultralytics/ultralytics)
[![License](https://img.shields.io/badge/License-CC-green.svg?style=for-the-badge)](https://creativecommons.org/licenses/by-nc/4.0/deed.en)

This repository contains the dataset for detecting road traffic signs in Vietnam using the state-of-the-art **YOLO** object detection model.

<p align="center">
  <img src="illustration.webp" alt="Viet Nam Traffic Sign" width="600">
</p>

---

## 📂 Repository Structure

The dataset is structured in the standard YOLO format, containing images and corresponding annotations divided into training, validation, and testing sets.

```text
├── classid.xlsx        # Excel file mapping class IDs to names
├── dataset/
│   ├── train/          # Training split
│   │   ├── images/     # Raw images (.jpg)
│   │   └── labels/     # Normalized bounding box coordinates (.txt)
│   ├── val/            # Validation split
│   │   ├── images/
│   │   └── labels/
│   └── test/           # Testing split
│       ├── images/
│       └── labels/
└── README.md
```

---

## 📊 Dataset Distribution

The dataset statistics below show the division of images and labels across the different splits:

| Split          |   Images   | Details                                                |
| :------------- | :--------: | :----------------------------------------------------- |
| **Train**      | **8,125**  | 8,124 labeled images + 36 background (negative) images |
| **Validation** | **1,016**  | 1,014 labeled images + 2 background (negative) images  |
| **Test**       | **1,016**  | 1,014 labeled images + 2 background (negative) images  |
| **Total**      | **10,157** |                                                        |

---

## 🏷️ Annotation Format

Annotations follow the standard **YOLO format**. For every image (e.g., `0002.jpg`), there is a corresponding label file (e.g., `0002.txt`) in the `labels/` directory.

Each row in the text file represents a single bounding box formatted as:

```text
<class_id> <x_center> <y_center> <width> <height>
```

- **`class_id`**: Integer representing the target class index (ranging from `0` to `81`).
- **`x_center`, `y_center`**: Center coordinates of the bounding box, normalized to `[0.0, 1.0]` by dividing by the image's width and height.
- **`width`, `height`**: The width and height of the bounding box, normalized to `[0.0, 1.0]`.

---

## 🚦 Supported Traffic Sign Classes (82 Classes)

The dataset contains **82 categories** of road signs commonly found on Vietnamese streets:

![Class distribution](class_distribution.png)

---
