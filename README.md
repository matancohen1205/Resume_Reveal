# Resume_Reveal

**Resume Seniority Classification**  
Predict seniority level from resume text and job role.


##  📖 Overview

Recruiters and HR systems often struggle to assess candidate seniority from free-form resumes and job descriptions, leading to slow and error-prone review processes.
Resume_Reveal tackles this by automating seniority classification (Junior, Mid, Senior) based on the combined analysis of resume text and job title, using a hybrid NLP pipeline that integrates fine-tuned deep learning models (e.g., RoBERTa), and GPT-4 prompt-based zero-shot classification to robustly infer candidate seniority levels. We collect and label data accordingly, train models (TF-IDF, DistilBERT, RoBERTa), and evaluate GPT-4’s prompt-only performance—achieving up to 90.6% accuracy with RoBERTa.
The novelty of our approach lies in jointly leveraging structured (job title) and unstructured (resume) input, while combining fine-tuned transformer models, and zero-shot GPT-4 inference.

## 🎯 Project Goals
**-- Data Collection:** Extract and generate resume data with job roles and corresponding seniority levels.

**-- Data Annotation:** Label examples using scraping and manual verification.

**-- Baseline Modeling:** Train a TF-IDF + Logistic Regression classifier.

**-- Transformer Fine-Tuning:** Fine-tune DistilBERT and RoBERTa for sequence classification.

**-- Zero-shot Inference:** Evaluate GPT-4 on prompt-based predictions without fine-tuning.

## 🧠 Used Models
## 1. Baseline:
     -- TF-IDF + Logistic Regression
## 2. Models & Inference:     
       -- DistilBERT
           Fine-tuned for 10 epochs. Best result at epoch 10.

       -- RoBERTa
           Fine-tuned for 10 epochs. Best result at epoch 8.
           
       -- GPT-4
          Prompt-only inference with zero-shot classification.

## 📁 Dataset
**File: DATA.xlsx** - (Size: 584 Resumes & Job titles) - 

 -- Resume (free-text)
 
 -- Job Title
 
 -- Seniority Label (Junior, Mid, Senior)

**Sources:** - 

 -- Web scraping

 -- GPT-4 synthetic generation

 -- Manual filtering

 ## 📊 Example

```
**Job Title:** `Business Analyst` 

**Resume Snippet:** `" Summary   Senior Business Analyst with over 10 years of diverse IT experience in Project management..."` 

**Predicted Label:** `Senior`
 
```

##  📈 Results Summary

 | Model                        | Accuracy   | Best Epoch  | Validation Loss |
| ---------------------------- | ---------- | ----------- | --------------- |
| TF-IDF + Logistic Regression | 81.20%     | -           | -               |
| GPT-4 (prompt-only)          | 78.60%     | -           | -               |
| DistilBERT (fine-tuned)      | 87.18%     | Epoch 10    | 0.4026          |
| RoBERTa (fine-tuned)         | **90.60%** | **Epoch 8** | **0.3297**      |

**Evaluation:** Measure performance across all models using accuracy, loss, and confusion matrices.

**Best Model:** RoBERTa — achieved the highest validation accuracy (90.60%) after 8 epochs of fine-tuning.

##  📊 Graphical Abstract

   ![Project Flowchart](Results/FlowChart.png)
   
## 📁 Repository Structure

```

├── Proposal/
│   ├── Nlp final project presentation.pdf
│   ├── Resume reveal - Reveal seniority level.pdf
│   └── Resume reveal FIRST_PROP_NLP.pdf
│
├── Results/
│   ├── Evaluation.csv
│   ├── FlowChart.png
│   ├── GPT_training_results.csv
│   ├── RoBERTa_training_results.csv
│   ├── distilBERT_training_results.csv
│   └── evaluation_file.pdf
│
├── SRC/
│   ├── DATA.xlsx
│   ├── DATA_GENERATION_AND_SCRAPING.ipynb
│   ├── EDA+BASELINE.ipynb
│   ├── MODELS_NOTEBOOK.ipynb
│   └── README.md  
```

##  ⚙️ Installation

**Clone this repository**  
   ```bash
   git clone https://github.com/matancohen1205/Resume_Reveal.git
   cd Resume_Reveal/SRC
   ``` 
📌 Note: For GPT-4 inference, register to [OpenRouter](https://openrouter.ai/settings/keys) and set your API key in the notebook.

## 🤝 Team Members
Matan Cohen

Eden Menahem

Shira Shani

📌 Developed for the Natural Language Processing (NLP) course at Holon Institute of Technology (HIT)



