Fatty Liver Severity Classification using DenseNet121

📌 Project Overview
This project focuses on multi-class classification of fatty liver severity using ultrasound images. The goal is to replicate and compare results from a research paper using deep learning models.

We implemented a DenseNet121-based Convolutional Neural Network (CNN) and compared it with a reference paper that uses a hybrid CNN–GNN (RCNN) framework.

---

📄 Reference Paper
Title:
Fatty Liver Classification via Risk-Controlled Neural Networks Trained on Grouped Ultrasound Image Data

Link:
https://doi.org/10.1038/s41598-024-57386-3

---

🧠 Methodology

| Component                      | Details                                                                          |
| ------------------------------ | -------------------------------------------------------------------------------- |
| Model (Paper)                  | Hybrid CNN + Graph Neural Network (DenseNet121 + GAT/GIN)                        |
| Model (Trained on our dataset) | DenseNet121 (Pretrained CNN with Transfer Learning)                              |
| Task                           | Multi-class Fatty Liver Severity Classification                                  |
| Input                          | Ultrasound Images                                                                |
| Dataset                        | https://www.kaggle.com/datasets/orvile/annotated-ultrasound-liver-images-dataset |

---

📂 Dataset

Ultrasound images categorized into:

* Benign
* Malignant
* Normal

Dataset split:

* 80% Training
* 20% Testing

---

⚙️ Model Details

🔹 Paper Approach

* Uses DenseNet121 as image encoder
* Integrated with Graph Neural Network (GAT/GIN)
* Uses grouped ultrasound images (patient-level)
* Applies conformal prediction (risk-controlled learning)
* Multi-class severity classification (2-class, 3-class, 4-class)

---

🔹 Our Approach (Trained same backbone model for comparative analysis)

* Uses DenseNet121
* Input: Raw ultrasound images
* Transfer learning applied
* End-to-end classification
* No graph-based aggregation

---

📊 Results

🔥 Overall Performance

| Metric               | Paper (DenseNet121 + GNN) | Trained on our dataset (DenseNet121) |
| -------------------- | ------------------------- | ------------------------------------ |
| Accuracy             | 79.2% (4-class)           | 77%                                  |
| Precision            | ~0.87–0.98                | 0.76 (weighted avg)                  |
| Recall (Sensitivity) | ~0.85–0.99                | 0.77                                 |
| F1-score             | ~0.86–0.98                | 0.76                                 |
| Specificity          | Not reported              | 0.8604                               |
| AUC Score            | ~0.95+                    | 0.8944                               |

---

📊 Class-wise Performance

| Class   | Precision | Recall | F1-score |
| ------- | --------- | ------ | -------- |
| Class 0 | 0.59      | 0.47   | 0.53     |
| Class 1 | 0.83      | 0.85   | 0.84     |
| Class 2 | 0.77      | 1.00   | 0.87     |

---

📉 Confusion Matrix

[[19 15 6]
[13 74 0]
[ 0  0 20]]

---

🧠 Analysis & Insights

🔥 1. Competitive Performance
Our model achieves 77% accuracy, which is very close to the paper (~79.2%)

Reasons:

* Strong feature extraction capability of DenseNet121
* Effective transfer learning

---

⚠️ 2. Model Architecture Difference
Paper uses CNN + GNN (advanced hybrid model)
Our model uses CNN only

👉 This explains performance gap

---

🔥 3. Strong Feature Learning
High AUC score (0.8944)
Indicates strong class separability

---

⚠️ 4. Class Imbalance Issue
Lower recall for Class 0 (0.47)
Perfect recall for Class 2 (1.00)

👉 Model favors certain classes

---

📉 5. Simpler Model vs Complex Model

| Aspect     | Paper                       | Our dataset result |
| ---------- | --------------------------- | ------------------ |
| Model      | CNN + GNN                   | CNN only           |
| Data Type  | Multi-image (patient-level) | Single image       |
| Accuracy   | Slightly higher             | Competitive        |
| Complexity | High                        | Moderate           |

---

🧠 Key Insight

Paper focuses on improving accuracy using **graph-based relational learning**

Our model shows that **DenseNet121 alone can achieve competitive performance** even without complex architecture

---

🎯 Conclusion

The DenseNet121-based model achieved 77% accuracy, which is comparable to the 79.2% reported in the reference paper. Although the paper uses a hybrid CNN–GNN architecture for improved performance, the standalone DenseNet121 model demonstrates strong capability in fatty liver classification using ultrasound images.

However, the absence of graph-based learning and smaller dataset size limit the overall performance. Incorporating advanced architectures could further improve results.

---

🚀 Future Work

* Integrate Graph Neural Networks (GNN)
* Increase dataset size
* Apply class balancing techniques
* Improve minority class detection
* Explore multimodal learning

---

👨‍💻 Author

Project developed as part of research on Fatty Liver Severity Detection using Deep Learning

---
