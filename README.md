# Tree Classification using Deep Learning & Texture Features

## Overview
This project classifies images into tree and non-tree categories using a hybrid approach combining **deep learning (CNN)** and **handcrafted texture features**. The model utilizes **ResNet50** for feature extraction and integrates texture-based features for improved classification accuracy.

## Features
- **Image Enhancement**: CLAHE (Contrast Limited Adaptive Histogram Equalization) to enhance contrast.
- **Texture Feature Extraction**:
  - **Gabor Filters**
  - **Gray Level Co-occurrence Matrix (GLCM)**
  - **Local Binary Patterns (LBP)**
  - **Histogram of Oriented Gradients (HOG)**
  - **SIFT Features** (Scale-Invariant Feature Transform)
- **Custom Data Generator**: Combines CNN-extracted features with handcrafted features.
- **Deep Learning Backbone**: ResNet50-based CNN for spatial feature learning.
- **Data Augmentation**: Image transformations (rotation, zoom, flipping, brightness adjustments).

## Dataset
The dataset is organized into two categories:
- `train/` : Training images (tree and non-tree)
- `val/` : Validation images (tree and non-tree)

## Model Architecture
The model consists of two parallel inputs:
1. **CNN Branch**: ResNet50 extracts spatial features.
2. **Handcrafted Feature Branch**: Dense layers process texture-based features.
3. **Fusion**: Both feature vectors are concatenated and passed through fully connected layers.

## Training Strategy
- **Loss Function**: Binary Cross-Entropy
- **Optimizer**: Adam (learning rate 0.0001)
- **Class Balancing**: Class weights computed for handling imbalance
- **Callback**: ReduceLROnPlateau for adaptive learning rate reduction

## Results
- Model trained for **8 epochs**.
- Achieved 97% accuracy in distinguishing trees from non-trees.

## How to Use
### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/tree-classification.git
cd tree-classification
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Train the Model
```python
python train.py
```

### 4. Run Inference
```python
python predict.py --image path/to/image.jpg
```

## Saved Model
The trained model is too large to be stored on GitHub. You can download it from Google Drive:
[Download Model (tree_detection_model.h5)](https://drive.google.com/file/d/1NlGJ_tjeh8Yc-iCEaFJNAyub_1vjSeed/view?usp=drive_link)

## Future Improvements
- Improve classification accuracy with additional feature engineering.
- Deploy as a web app using Flask or FastAPI.

## Contributing
Feel free to open issues and submit pull requests.

## License
This project is open-source under the MIT License.

---

### Connect with Me
If you have any feedback or suggestions, feel free to reach out on [LinkedIn](https://www.linkedin.com/in/kaushal-kathiriya-17a854289/).

