# 🍎 Fruit Classification with MobileNetV2  

![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow)  
![Keras](https://img.shields.io/badge/Keras-Deep%20Learning-red?logo=keras)  
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)  

## 🚀 Demo on Hugging Face

You can try the model directly on Hugging Face Spaces:  
👉 [Click here to open the demo](https://huggingface.co/spaces/yasinxz/Fruit_veg_scanner)



## 📌 Overview  
This project implements a **fruit classification system** using **transfer learning** with **MobileNetV2**.  
The model was trained on a dataset of fruit images, achieving an accuracy of **~90%** on the validation set.  

---

## ✨ Features  
- ✅ Image preprocessing with **data augmentation**  
- ✅ Transfer learning using **MobileNetV2**  
- ✅ Custom dense & dropout layers to reduce overfitting  
- ✅ Training visualization (accuracy curves)  
- ✅ Model saved in `.keras` format for reuse  

---

## 📂 Dataset Structure  
```
archive/
├── train/          # Training images
├── validation/     # Validation images
└── test/           # Test images
```
Each folder must contain subfolders for fruit classes (e.g., `apple`, `banana`, `orange`).  

---

## ⚙️ Methodology  

1. **Data Preprocessing**  
   - Normalization (rescaling pixel values).  
   - Data augmentation: rotation, shift, shear, zoom, flip, brightness.  

2. **Model Architecture**  
   - Base: `MobileNetV2` (pre-trained, frozen).  
   - Added layers:  
     - GlobalAveragePooling2D  
     - Dense(64) + Dropout(0.25)  
     - Dense(128) + Dropout(0.3)  
     - Dense(256) + Dropout(0.4)  
     - Dense(num_classes, softmax)  

3. **Compilation & Training**  
   - Optimizer: Adam  
   - Loss: Sparse Categorical Crossentropy  
   - Metric: Accuracy  
   - Epochs: 100  

4. **Results**  
   - Training Accuracy: ~89.9%  
   - Validation Accuracy: ~93.1%  
   - Final model saved as `fruit_model.keras`  

---

## 📊 Results  

| Metric              | Value   |
|----------------------|---------|
| Training Accuracy    | ~89.9%  |
| Validation Accuracy  | ~93.1%  |
| Final Test Accuracy  | ~90%    |

📈 Accuracy curves:  
The training and validation accuracy were plotted over 100 epochs, showing stable convergence without overfitting.  

---

## 🚀 How to Run  

### 1. Clone the repository  
```bash
git clone <repo-url>
cd fruit-classification
```

### 2. Create a virtual environment  
```bash
python -m venv venv
source venv/bin/activate    # Linux/Mac
venv\Scripts\activate     # Windows
```

### 3. Install dependencies  
```bash
pip install -r requirements.txt
```
Or install manually:  
```bash
pip install tensorflow matplotlib pandas
```

### 4. Prepare the dataset  
Make sure the dataset is in `archive/` with `train`, `validation`, and `test` subfolders.  

### 5. Run the notebook  
```bash
jupyter notebook Untitled.ipynb
```

### 6. Train the model  
- Trains for 100 epochs.  
- Saved as `fruit_model.keras`.  

### 7. Evaluate the model  
- Test set evaluation (~90% accuracy).  
- Accuracy/loss plots generated automatically.  

---

## 🔮 Future Improvements  
- Fine-tune MobileNetV2 layers for higher accuracy.  
- Use larger and more diverse fruit datasets.  
- Deploy as a **web or mobile app** for real-time fruit recognition.  

---

✍️ Developed with **Python + TensorFlow/Keras**.  



