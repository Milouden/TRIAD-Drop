# TRIAD-Drop
RAG-powered multimodal framework for student dropout prediction in distance learning with explainable interventions

# TRIAD-Drop: Transformative AI for Student Retention

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> "Early warning system combining Retrieval-Augmented Generation, cross-modal fusion, and explainable interventions for distance education"

<img src="docs/pipeline.png" alt="TRIAD-Drop Architecture" width="600"/>

## 🔍 Overview
TRIAD-Drop is an end-to-end framework that predicts student dropout risk in distance learning by integrating:
- **RAG-enhanced sentiment analysis** grounded in pedagogical knowledge
- **Prompt-engineered academic stress detection**
- **Cross-modal attention fusion** of behavioral, demographic, and affective signals
- **Source-cited intervention recommendations**

Achieves **89% accuracy** and **40% lower calibration error** than traditional models on real-world datasets.

## 📦 Dataset
Uses augmented version of the [Predict Students' Dropout and Academic Success](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success) dataset:
- Original: 4,423 students, 36 features
- Augmented: Synthetic student comments generated via GPT-4.5
- Features: Socio-demographics, academic performance, forum comments

```python
# Sample synthetic comment generation
prompt = f"As a {age}-year-old {gender} student with GPA {gpa}, write forum post about {course}"
synthetic_comment = gpt4.generate(prompt)
```

## 🛠 Installation
```bash
git clone https://github.com/yourusername/TRIAD-Drop.git
cd TRIAD-Drop
pip install -r requirements.txt
```

## 🚀 Usage
1. **Train model**:
```python
from triad import TriadModel
model = TriadModel()
model.train("data/augmented_dataset.csv")
```

2. **Generate interventions**:
```python
risk_report = model.predict(student_profile)
print(risk_report.rationale)
# "At week 5: 'I feel isolated' → FAQ §3.1 → Risk 0.78 → Suggest mentorship"
```

3. **Export dashboard**:
```bash
python -m triad.visualize export_dashboard
```

## 📊 Results
| Model          | Macro-F1 | ECE   | Latency |
|----------------|----------|-------|---------|
| XGBoost        | 0.74     | 0.071 | 2.1ms   |
| TRIAD-Drop (Ours) | **0.85** | **0.042** | 14.2ms |

## 📚 Citation
```bibtex
@inproceedings{mihoubi2025triaddrop,
  title={BEYOND CLASSICAL AND CONTEMPORARY MODELS: A
TRANSFORMATIVE AI FRAMEWORK FOR STUDENT
DROPOUT PREDICTION IN DISTANCE LEARNING USING
RAG, PROMPT ENGINEERING, AND CROSS-MODAL
FUSION},
  author={Mihoubi, Miloud and Zerkouk, Meriem and Chikhaoui, Belkacem},
  booktitle={Canadian Conference on Artificial Intelligence},
  year={2025}
}
```

## 📄 License
This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.
