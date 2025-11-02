# 🐱🐶 Cats vs Dogs Classifier

This project is a computer vision model built using **FastAI** to classify images as either "Cat" or "Dog".

---

## 📘 Project Overview
The goal of this project is to develop an AI model capable of distinguishing cat and dog images with high accuracy.  
The dataset was collected from the internet and processed using FastAI tools.

---

## 🧰 Tools & Technologies
- Python 3.11  
- FastAI  
- Jupyter Notebook  
- Pillow  
- pathlib  

---

## ⚙️ Project Steps
1. **Data Collection:**  
   - Images of cats and dogs were downloaded using `search_images` from FastAI.
   - Verified image quality using:
     ```python
     failed = verify_images(get_image_files(path))
     failed.map(Path.unlink)
     ```
2. **Data Preparation:**  
   - Created a `DataBlock` for image classification.
3. **Model Training:**  
   - Trained using:
     ```python
     learn.fine_tune(3)
     ```
4. **Model Export:**  
   - Saved the trained model as:
     ```python
     learn.export('models/cats_vs_dogs_model.pkl')
     ```
5. **Prediction:**  
   - Test new images using:
     ```python
     pred_class, pred_idx, pred_probs = learn.predict(PILImage.create('image.jpg'))
     print(pred_class, pred_probs[pred_idx])
     ```

---

## 📁 Project Structure
cats-vs-dogs/
├── notebook.ipynb
└── README.md

---

## 📊 Results
- Model accuracy: **≈99.98%**  
- Example output:
