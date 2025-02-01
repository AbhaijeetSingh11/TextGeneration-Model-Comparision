# Model Comparison using TOPSIS

## Overview
This project evaluates different text-generation models using various performance metrics and applies **TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution)** to rank them objectively.

## Models Compared
- **DistilGPT-2** (`distilbert/distilgpt2`)
- **GPT-2** (`gpt2`)
- **DialoGPT-Medium** (`microsoft/DialoGPT-medium`)
- **RuGPT3-Small** (`ai-forever/rugpt3small_based_on_gpt2`)
- **GPT2-Large** (`openai-community/gpt2-large`)

## Evaluation Metrics
The models are evaluated based on the following metrics:

| Parameter               | Description |
|-------------------------|-------------|
| **Avg F1-score**        | Measures precision and recall of generated text |
| **Avg ROUGE-1**         | Unigram overlap with reference text |
| **Avg ROUGE-2**         | Bigram overlap with reference text |
| **Avg ROUGE-L**         | Longest common subsequence similarity |
| **Diversity Score**     | Measures diversity in generated text (1 - Jaccard Similarity) |
| **Avg Response Length** | Measures verbosity of the generated response |

## TOPSIS Parameters
| Parameter               | Weight | Impact |
|-------------------------|--------|--------|
| **Avg F1-score**        | 0.25   | **+**  |
| **Avg ROUGE-1**         | 0.20   | **+**  |
| **Avg ROUGE-2**         | 0.15   | **+**  |
| **Avg ROUGE-L**         | 0.15   | **+**  |
| **Diversity Score**     | 0.15   | **+**  |
| **Avg Response Length** | 0.10   | **-**  |

## Installation & Setup
### 1. Install Required Dependencies
```sh
pip install transformers rouge-score numpy scikit-learn pandas topsis-python
pip install 102217186_abhaijeet_topsis==1.0.0
```

### 2. Run Model Evaluation
```sh
python Model_comparision_TextGeneration.ipynb
```
This generates `model_comparison_results.csv` with model performance scores.

### 3. Apply TOPSIS
```sh
python -m 102217186_abhaijeet_topsis "model_comparison_results.csv" "0.25,0.20,0.15,0.15,0.15,0.10" "+,+,+,+,+,-" "output.csv"
```
This generates `output.csv` with the TOPSIS ranking of the models.

## Output
- **`model_comparison_results.csv`** → Contains raw evaluation results.
- **`output.csv`** → Contains final rankings using TOPSIS.

## Output file
![image](https://github.com/user-attachments/assets/5165f1b9-c0d7-4fb4-aaab-112b9d59b2b6)

## Model comparision for Text Generating Models
![topsis_models_comparison](https://github.com/user-attachments/assets/d6a1b84e-c2ed-44ff-91f8-e1280f0b0c38)

## Authors
- **Abhaijeet Singh** (asingh37_be22@thapar.edu)

## License
This project is licensed under the MIT License.

