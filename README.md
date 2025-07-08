# Text-Intent-Classifier
This project builds an intelligent text classification model to automatically categorize short English messages into one of the following intent categories:

- **Complaint**
- **Inquiry**
- **Suggestion**
- **Thank You**

The model is designed for real-world applications such as customer service, feedback analysis, or helpdesk automation — where understanding the intent behind a message is critical for routing and response handling.
##  Features
-  **Classifies text messages** into: `Complaint`, `Inquiry`, `Suggestion`, or `Thank You`
-  Fine-tuned using **manually labeled high-quality data** and scaled with **confidence-based pseudo-labeling**
-  Built on **DeBERTa-v3**, a powerful transformer model for deep contextual understanding
-  Includes **two user interfaces** via Gradio:
  1. **Single Message Classifier**  
     → Instantly test short texts and view predicted intent with confidence score
  2. **Review File Filter Tool**  
     → Upload `.csv` or `.xlsx` files  
     → Filter messages by specific intent and set a confidence threshold  
     → Download filtered results as Excel file
  3. Accuracy of model : 92% , Macro F1 Score: 0.94
##  Dataset
All data used in this project is based on the `test.jsonl` file from the [SetFit/amazon_reviews_multi_en](https://huggingface.co/datasets/SetFit/amazon_reviews_multi_en) dataset.
- A custom set of **100 labeled examples** (25 per class) was created:
  - Selected from `test.jsonl` and partially written manually.
- The remaining entries from `test.jsonl` were treated as **unlabeled**, and later pseudo-labeled by the model.
  - Only predictions with **confidence > 90%** were used for training.
## Model Architecture
- Base model: [`microsoft/deberta-v3-base`](https://huggingface.co/microsoft/deberta-v3-base)
- Fine-tuned using Hugging Face `Trainer`
- Evaluation results on test split (191 samples)

  
