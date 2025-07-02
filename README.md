# 🧠 Face Recognition Project
Deep Learning School final project (MIPT). Face detection, alignment and recognition.

**The goal of this project is to build a complete face recognition system** that includes detection, alignment, and vector representation of faces for further comparison.

---

## 📌 Project Stages

### 1. Face Detection

The first step processes an image (e.g., from surveillance footage) and detects all the faces using a pretrained detector (e.g., `insightface`). Each detected face (bounding box) is then processed separately.

---

### 2. Face Alignment

After detection, **face alignment** is performed in two steps:

1. Key facial landmarks (eye centers, nose tip, mouth corners) are predicted using a Stacked Hourglass Network.
2. The face is rotated and scaled so that:
   - the eyes lie on a horizontal line,
   - the distance between the eyes is fixed.

---

### 3. Face Recognition (Embedding)

The goal is to train a neural network that **maps a face to a vector (embedding)** such that:
- embeddings of the **same person** are close,
- embeddings of **different people** are far apart (e.g., using cosine distance).

❗ We **don’t train a regular classifier** with one class per person. Instead, we want a model that works on **unseen identities**. Model that is be able to handle faces of people who are not present in the training data. We want it to produce **close embeddings** for different photos of the **same person**, and **distant embeddings** for faces of **different people**.

---

## ✅ Completed Assignments

### 📓 Assignment 1 — Face Classification and ArcFace

> Notebook: `Face_Classification_ArcFace_Embeddings.ipynb`

**Plan:**
- ✅ Choose a model pretrained on ImageNet
- ✅ Train it using cross-entropy loss → achieve accuracy > 0.7
- ✅ Implement and train with **ArcFace loss** → accuracy > 0.7

---

### 📓 Assignment 2 — Facial Landmarks and Alignment

> Notebook: `Face_Alignment_Hourglass_Network.ipynb`

**Plan:**
- ✅ Implement Hourglass block
- ✅ Implement the Stacked Hourglass architecture
- ✅ Convert landmark points to heatmaps
- ✅ Train the model to predict heatmaps
- ✅ Implement face alignment based on predicted landmarks

---

### 📓 Assignment 3 — Full Recognition Pipeline

> Notebook: `Face_Recognition_Pipeline.ipynb`

**Plan:**
- ✅ Build a full face recognition pipeline:
  - Use `insightface` for detection,
  - Use model from Assignment 2 for alignment,
  - Use model from Assignment 1 for embeddings
- ✅ Input: image with multiple faces
- ✅ Output: list of embeddings for all detected faces
- ✅ Demonstrate on same/different person examples using cosine distance

---