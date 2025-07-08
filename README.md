# Text-Intent-Classifier
This project builds an intelligent text classification model to automatically categorize short English messages into one of the following intent categories:

- **Complaint**
- **Inquiry**
- **Suggestion**
- **Thank You**


##  Featuresح
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
##  Dataset
- Source: [SetFit/amazon_reviews_multi_en](https://huggingface.co/datasets/SetFit/amazon_reviews_multi_en)
- Files used: `train.jsonl`, `test.jsonl`
- Final dataset includes:
  - **100 manually labeled messages** (25 per category)
  - **854 pseudo-labeled messages** (filtered at confidence > 90%)
  
## Model Architecture

- Base model: [`microsoft/deberta-v3-base`](https://huggingface.co/microsoft/deberta-v3-base)
- Fine-tuned using Hugging Face `Trainer`
- Evaluation results on test split (191 samples):
  
The model is designed for real-world applications such as customer service, feedback analysis, or helpdesk automation — where understanding the intent behind a message is critical for routing and response handling.
