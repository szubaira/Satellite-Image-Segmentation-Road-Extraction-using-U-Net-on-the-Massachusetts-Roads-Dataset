## **Satellite Image Segmentation: Road Extraction using U-Net on the Massachusetts Roads Dataset**

### **Project Overview**
This project addresses the challenge of automated feature extraction from high-resolution aerial imagery, specifically focusing on the segmentation of road networks. By leveraging a **U-Net architecture** and a subset of the **Massachusetts Roads Dataset**, the project successfully implemented a deep learning training loop to classify pixels as "road" or "background." The resulting model provides a foundational framework for automating geographic information system (GIS) updates and infrastructure monitoring.
<img width="918" height="245" alt="Screen Shot 2026-05-02 at 19 56 36" src="https://github.com/user-attachments/assets/86329e43-5078-4f07-9542-13fc79b93889" />

### **Business Understanding**
**Stakeholders:**
*   **Urban Planners and Municipal Governments:** To maintain up-to-date infrastructure records.
*   **Logistics and Navigation Companies:** To improve routing accuracy in rapidly developing areas.
*   **Emergency Response Services:** To identify accessible routes following natural disasters.

**Business Problem:**
Manual labeling of road networks from satellite imagery is labor-intensive, expensive, and subject to human error. Developing a robust, automated segmentation tool reduces the "time-to-map," allowing organizations to respond faster to infrastructure changes. 
> **Research Citation:** This project builds upon the methodology established by Volodymyr Mnih in his seminal work: *Mnih, V. (2013). Machine Learning for Aerial Image Labeling. University of Toronto.*[cite: 12]

### **Data Understanding**
The analysis utilized a curated subset of the **Massachusetts Roads Dataset**.
*   **Data Source:** Aerial imagery of the state of Massachusetts, originally compiled by the University of Toronto[cite: 12].
*   **Volume:** The subset consists of **200 high-resolution images** and their corresponding binary masks, extracted from the original collection of 1,171 images[cite: 12].
*   **Specifications:** Each image is **1500 × 1500 pixels**, representing a physical ground area of **2.25 square kilometers**[cite: 12].
*   **Limitations:** The use of a 200-image subset may limit the model's exposure to diverse environmental conditions (e.g., heavy forest cover or varied weather) compared to the full dataset. Additionally, the high resolution requires significant computational resources for processing.
<img width="834" height="294" alt="Screen Shot 2026-05-02 at 19 57 02" src="https://github.com/user-attachments/assets/d6082ec1-2a79-49cc-bc83-067a2c38c447" />

### **Modeling and Evaluation**
The project implemented a deep learning pipeline using **PyTorch** and specialized libraries for computer vision.
*   **Architecture:** A **U-Net** architecture was selected for its proven efficacy in medical and satellite image segmentation, where preserving spatial context is critical[cite: 12].
*   **Implementation:** The training loop was constructed using a custom **train function and evaluator**[cite: 12].
*   **Augmentation:** The **Albumentations** library was integrated to perform image transformations, improving model generalization[cite: 12].
*   **Metrics:** Model performance was evaluated based on its ability to minimize loss during the training loop and maximize pixel-wise accuracy between the predicted masks and the ground truth.
<img width="840" height="420" alt="Screen Shot 2026-05-02 at 19 57 44" src="https://github.com/user-attachments/assets/598b856e-6751-40b9-8b7a-df1ebb3c5fe5" />

### **Conclusion**
The project successfully demonstrates that the U-Net architecture can effectively learn complex road patterns from high-resolution aerial data. 

**Recommendations:**
*   **Scale the Training Data:** To improve the model's reliability, the pipeline should be deployed on the full 1,171-image Massachusetts dataset.
*   **Hyperparameter Optimization:** Further tuning of the learning rate and batch size within the current training function could yield higher segmentation precision.

**Future Steps:**
*   **Backbone Integration:** Incorporate pre-trained encoders (such as ResNet or EfficientNet) within the U-Net structure to accelerate convergence.
*   **Real-world Testing:** Expand the model's application to diverse geographical regions outside of Massachusetts to test its transfer learning capabilities.
