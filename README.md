# SSD-YOLOV12
# ❄️ YOLOv12 Object Detection on Snowy Windshield Scenes

## 🧠 Project Summary

This project focuses on fine-tuning the **Ultralytics YOLOv12 (SSD-YOLO)** model to detect multiple object classes in difficult visual conditions — primarily snowy or blurred windshield views from vehicle cameras. It is designed to improve autonomous vehicle perception in challenging winter conditions.

---

## 📂 Dataset Overview

- **Total Images**: 31,676  
- **Annotation Format**: YOLO TXT (12 classes)  
- **Split**:  
  - `Train`: 70%  
  - `Validation`: 15%  
  - `Test`: 15%  
- **Resolution**: 640×640  
- **Classes**:
  - Car, Truck, Pedestrian, Biker  
  - Traffic light (Red, Yellow, Green) & their Left variants  
  - Stop sign (`arret`)

---

## ⚙️ Model and Training Details

| Detail | Value |
|--------|-------|
| **Model** | YOLOv12s (SSD-YOLO, pretrained) |
| **Backbone** | ResNet-50 |
| **Training Time** | ⏱️ 10.39 hours |
| **Batch Size** | 8 |
| **Epochs** | Auto-stopped via early stopping |
| **Hardware** | NVIDIA GeForce RTX 4050 Laptop GPU (6GB VRAM) |

---

## 📈 Evaluation Results (on Test Set)

| Metric         | Value     |
|----------------|-----------|
| **mAP@0.5**     | `0.586`   |
| **mAP@0.5:0.95**| `0.341`   |
| **Precision**   | ~0.65 avg |
| **Recall**      | ~0.56 avg |
| **Inference Speed** | ~8.2 ms/image |

### 🔍 Per-Class Sample Results

| Class                     | mAP@0.5 |
|--------------------------|---------|
| Car                      | 0.841   |
| Truck                    | 0.824   |
| Pedestrian               | 0.658   |
| Traffic Light (Green)    | 0.413   |
| Traffic Light (Red Left) | 0.433   |
| Arret (Stop Sign)        | 0.478   |

---

## 🖼️ Inference Example

Example prediction on a test image (416×640):

Detected: 1 Car, 1 Traffic Light - Yellow, 1 Traffic Light - Yellow Left
Speed: 3.6ms preprocess, 9.9ms inference, 2.9ms postprocess
> 📂 See `runs/train/ssd_yolov12_project*/` for full visual results and saved weights.

---

## 📃 Files in This Repository

| File / Folder              | Description |
|---------------------------|-------------|
| `yolov12_project.ipynb`    | Full notebook with training, evaluation, and inference |
| `short_report.md`          | Project report (Markdown version) |
| `report.docx`              | Word version of project report for faculty submission |
| `data.yaml`                | Dataset class config |
| `runs/`                    | Folder containing training results, inference images, model weights |

## 🧑 Author

**PRABHATH KOLLI**  
B.Tech Data Science & AI  
IIT Roorkee  
Graduating July 2027

---

## 📌 Notes

- This project was developed as part of a university computer vision assignment.
- Final model trained on local GPU with PyTorch + Ultralytics YOLOv12 (v8.3.137).

> For any queries, contact via GitHub or email.
