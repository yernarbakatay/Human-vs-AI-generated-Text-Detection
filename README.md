# Human-vs-AI-generated-Text-Detection

This project explores two different approaches for detecting AI-generated text:

1. LLM prompting-based classification  
2. Transformer fine-tuning using RoBERTa  

The project compares modern prompting pipelines against task-specific transformer models while also investigating parameter-efficient optimization techniques such as LoRA and layer freezing.

---

# Dataset

The original raw dataset can be downloaded from the following HuggingFace repository:

https://huggingface.co/datasets/gsingh1-py/train/tree/main

After downloading the raw dataset, the preprocessing pipeline used in this project can be reproduced using:

`CSE881_Project_Preprocessing.ipynb`

This notebook performs the preprocessing steps described in our report, including:

- reshaping the dataset from wide to long format
- generating binary classification labels
- extracting standardized text segments
- filtering short responses
- preparing cleaned data for experimentation

After preprocessing, the dataset was further reduced and balanced using:

`sampling.ipynb`

This notebook creates the final sampled dataset used for experimentation while preserving representative class distributions.

---

# Repository Structure

## Data-related notebooks

### `CSE881_Project_Preprocessing.ipynb`
Main preprocessing pipeline used to transform the raw dataset into the cleaned format used throughout the project.

### `sampling.ipynb`
Creates the final sampled dataset used for experimentation and model training.

---

# Experimental Approaches

## 1. LLM Prompting Approach

The following notebooks were used for the prompting-based AI detection pipeline:

### `Llama3_1_prompting_ai_vs_human.ipynb`
Main LLaMA 3.1 prompting experiments for AI-vs-human classification.

### `Vanilla_COT_stepback.ipynb`
Contains experiments for:
- Vanilla prompting
- Chain-of-Thought (CoT) prompting
- Stepback prompting

### `julia-initial-eda.ipynb`
Initial exploratory analysis and experimentation related to prompting strategies.

### `testing-ollama-locally.ipynb`
Notebook for testing and running local Ollama-based inference.

---

## 2. RoBERTa Fine-Tuning Approach

### `RoBERT.ipynb`
Main transformer fine-tuning pipeline using RoBERTa.

This notebook includes:
- tokenization
- supervised fine-tuning
- layer freezing experiments
- LoRA / PEFT experiments
- efficiency vs. accuracy analysis
- visualization and evaluation metrics

---

# Notebook Preview Notes

Most notebooks in this repository can be fully viewed directly through the GitHub notebook preview, including both code and generated outputs.

However, due to visualization widget metadata used in:

- `CSE881_Project_Preprocessing.ipynb`
- `RoBERT.ipynb`

GitHub may fail to render these notebooks correctly in-browser.

If this occurs, please download the notebooks locally and open them in Jupyter Notebook or Google Colab to view the complete outputs and visualizations.

---

# Slides

Project presentation slides:

https://docs.google.com/presentation/d/1PEiGGrY1hKQDf_pDyqy5WhHbj7-aGS1JpDDtdJnv6Hc/edit?slide=id.g3d741dfe386_4_0#slide=id.g3d741dfe386_4_0

---

# Processed Dataset

Processed dataset used for experiments:

https://michiganstate-my.sharepoint.com/:x:/r/personal/bakatayy_msu_edu/Documents/class%20project/final_dataset.csv?d=wd57df9624b7749fcb7f9767b07841832&csf=1&web=1&e=mCcxkH
