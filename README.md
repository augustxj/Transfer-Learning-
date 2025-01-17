# **Transfer Learning for Lymphocyte and Monocyte Classification**

This project applies Transfer Learning to classify images of white blood cells (WBC) into two categories: Lymphocytes and Monocytes. It compares the performance of a baseline model trained from scratch with a Transfer Learning model based on the VGG16 architecture. The primary focus is on evaluating and improving classification accuracy; however, I encountered some challenges, such as class bias and possible overfitting.

Feel free to fork the repository and improve it in any way. Your input will be incredibly valuable for my learning process.

I have added some comments on areas that could be improved to achieve optimal results, but as I mentioned, I'm a student, so I may not have gotten everything right.

---

## **Dataset**

The dataset was adapted from the [White Blood Cells Dataset on Kaggle](https://www.kaggle.com/datasets/masoudnickparvar/white-blood-cells-dataset?select=Train). Initially divided into `Train` and `Test` folders, it was rearranged into a format compatible with this project using a Python script. Each class (Lymphocyte and Monocyte) contains up to 300 images due to RAM problems.

---

## **Project Workflow**

### **1. Baseline Model**
- Built a convolutional neural network (CNN) from scratch.
- The model contains:
  - 4 convolutional layers alternating with max-pooling layers.
  - Fully connected layers with dropout for regularization.
  - Softmax activation for classification.
- Achieved **94% accuracy** on the test set.

### **2. Transfer Learning Model**
- Utilized the pre-trained **VGG16** network:
  - Replaced the final layer with a softmax layer for binary classification.
  - Fine-tuned the last layer while freezing earlier layers.
- Achieved **82% accuracy**, with improved generalization compared to the baseline.

---

## **Key Results**

### **Baseline Model**
- High accuracy (94%) but potential **class bias** observed.
- Precision and recall indicate overfitting towards the monocyte class.

### **Transfer Learning Model**
- Moderate accuracy (82%) with balanced F1-scores across classes.
- Demonstrated potential for generalization but requires further fine-tuning.

---

## **Challenges and Observations**

1. **Class Bias:**
   - Both models tend to favor the monocyte class due to visual similarities between lymphocytes and monocytes.
   
2. **Dataset Challenges:**
   - Small dataset size limits the models' ability to generalize.
   - Balanced class distribution was ensured during preprocessing.

3. **Improvement Opportunities:**
   - Apply **data augmentation** to increase diversity.
   - Adjust **class weights** to penalize misclassifications of lymphocytes.
   - Experiment with fine-tuning more layers in the Transfer Learning model.

---

## **How to Run the Project**

1. **Setup Environment:**
   - Install required libraries (TensorFlow, Keras, etc.).
   - Clone the repository:
     ```
     git clone https://github.com/augustxj/Transfer-Learning-.git
     ```
2. **Preprocess Dataset:**
   - Run the provided script to rearrange dataset folders.
3. **Train Models:**
   - Execute the notebook to train both baseline and Transfer Learning models.
4. **Evaluate Performance:**
   - Use validation and test sets to analyze accuracy, loss, and bias.
5. **Predict New Images:**
   - Use the provided function to classify uploaded images.

---

## **Contact**

For questions, suggestions, or feedback, feel free to contact me:

**João Gonzaga**  
joao.gonzaga@sou.unifal-mg.edu.br

---

