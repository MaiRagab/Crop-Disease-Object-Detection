# 🌿 Crop Disease Detection System (YOLOv8)

## 📌 Project Overview
This project is an AI-based **Crop Disease Detection System** built using **YOLOv8 (Ultralytics)** for real-time object detection in agricultural images.  
The system identifies and classifies plant conditions into four categories:

- Leaf Disease  
- Fruit Disease  
- Pest  
- Healthy  

It can also count infected regions and provide disease-type classification per image.

---

## 👩‍💻 Project Member
**Mai Ragab Khalaf**  
ID: 2023036969  

---

## 📊 Dataset

The dataset was obtained from **Roboflow** :contentReference[oaicite:0]{index=0} under the name *Crop Disease Computer Vision Model*.

Originally, it contained **23 classes**, which were grouped into:

- Leaf Disease  
- Fruit Disease  
- Pest  
- Healthy  

### Dataset Format
- Annotation format: **YOLO**
- Each label contains:
  - Class ID  
  - Bounding box (x_center, y_center, width, height)

### Dataset Split
- Training: 4200 images  
- Validation: 360 images  
- Testing: 250 images  

This grouping helped reduce class imbalance and improved model generalization.

---

## 🚀 Model Architecture

The model is based on **YOLOv8 Nano (YOLOv8n)** developed by :contentReference[oaicite:1]{index=1}.

### Why YOLOv8n?
- Fast inference speed ⚡  
- Lightweight model  
- Suitable for real-time applications  
- Good balance between accuracy and performance  

The model was initialized with pretrained weights and fine-tuned using transfer learning.

---

## 🧠 Training Details

- Training strategy: **Transfer Learning**
- Epochs: 70 (early stopping applied)
- Early stopping patience: 20 epochs
- Best model saved at: **Epoch 32**
- Final stop at: **Epoch 52**

### Data Characteristics
- Natural augmentation (rotation, flipping, noise)
- No duplicate images
- Clean dataset (no major preprocessing required)

---

## 📈 Evaluation Results

The model achieved strong performance:

- **mAP@50:** 96.69%  
- **mAP@50-95:** 69.28%  
- **Precision:** 93.94%  
- **Recall:** 94.35%  

### Interpretation:
- High precision → low false positives  
- High recall → detects most objects  
- Strong mAP → accurate detection and localization  

---

## 🧪 Testing on Unseen Data

The model was tested on **50 unseen images** from the test set.

### Observations:
- Correct detection of diseased regions  
- Accurate classification of healthy crops  
- Strong generalization ability  
- Consistent bounding boxes and labels  

---

## 🔢 Infected Area Counting

The system can count infected regions per image by:
- Detecting all objects
- Filtering out "Healthy" class
- Counting only disease-related detections

This provides a clear estimate of infection severity in each image.

---

## 🧾 Disease Type Classification (Optional Feature)

The model also supports:
- Extracting disease labels per image  
- Grouping multiple detected diseases  
- Labeling images as:
  - Healthy  
  - Diseased (with disease type(s))  

This adds an extra layer of interpretability for agricultural analysis.

---

## 📎 Colab Notebook
You can view the full implementation here:

[Google Colab Notebook](https://colab.research.google.com/drive/1KMth2Lwe4guDUDH5X5sGhR4M-TMIgVQY?usp=sharing&utm_source=chatgpt.com)

---

## 🏁 Conclusion

This project demonstrates the effectiveness of YOLOv8 for agricultural disease detection.  
The system is capable of:
- Detecting plant diseases  
- Classifying crop conditions  
- Counting infected regions  
- Generalizing well to unseen data  

It can be extended for real-world precision agriculture applications.
