# MTGScan Cards

**MTGScan Cards** is an open-source project for detecting, identifying, and analyzing physical Magic: The Gathering cards using computer vision and machine learning.

This organization hosts the fullstack application, keypoint detection model, and feature extraction workflows used in the MTGScan pipeline.

---

## Repositories

### [`monolithic`](https://github.com/mtgscan-cards/monolithic)
> 🖥️ Fullstack web application for scanning and identifying MTG cards

- Built with React (frontend) and Flask (backend)
- Integrates OpenCV + TensorFlow.js for real-time card corner detection
- Supports scanning via desktop camera or mobile QR offloading
- PostgreSQL-based collection tracking and card database
- Dockerized for local or server deployment

---

### [`simple-mtg-keypoint-regression`](https://github.com/mtgscan-cards/simple-mtg-keypoint-regression)
> 📐 ML model for card quadrilateral corner prediction

- Heatmap-based keypoint regression using TensorFlow/Keras
- Trained on a synthetic dataset of MTG card images with randomized distortions
- Uses MobileNet or ResNet backbones with SoftArgmax decoding
- Outputs 4-point quadrilateral coordinates per frame
- Exportable to TensorFlow.js for WebGL inference w/ float16 quantization

---

### [`simple-mtg-feature-extraction`](https://github.com/mtgscan-cards/simple-mtg-feature-extraction/tree/production)
> 🧠 Feature extraction pipeline for card identification

- Uses OpenCV + SIFT/RootSIFT for feature vector generation
- Batch-processing pipeline that stores descriptors in HDF5
- Builds FAISS indices for fast visual similarity search
