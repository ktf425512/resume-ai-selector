# AI Resume Selector

**End-to-End AI-Powered Resume Screening & Matching System**

---

## 🚀 Project Overview

This project is a robust, fully automated AI pipeline for resume screening and matching.  
It combines GPT-powered natural language processing and semantic embeddings to select top candidates for any job description, based on semantic similarity to curated sample resumes.

---

## 📝 Data Privacy

*All resumes and job descriptions in this repository are fully synthetic, AI-generated, and do **not** contain real or sensitive personal data.  
This ensures full compliance for open-source and professional demonstration.*

---

## 📂 Project Structure
```
AI_RESUME_SCANNER/
├── JD/ # Job descriptions (PDF/DOCX)
├── original_resume/ # All candidate resumes
├── sample_resume/ # Ideal sample resumes (curated by user)
├── selected_resume/
│ └── YYYY-MM-DD/ # Output: selected resumes (by date)
├── .env # API key config (use .env.example as template)
├── main_ai_resume.ipynb # Main Jupyter notebook
├── requirements.txt # Python dependencies
└── README.md
```
---

## 🧠 Matching Logic & Scoring

- **AI Summaries:**  
  GPT-4 generates concise, job-focused summaries for each sample and candidate resume based on the job description (JD).
- **Semantic Embedding:**  
  All summaries are embedded using SentenceTransformer (`all-mpnet-base-v2`) for deep semantic matching.
- **Similarity Scoring:**  
  For each candidate, the max cosine similarity to any sample summary is used as their match score.
- **Selection Threshold:**  
  Only candidates above the threshold are selected, with filenames indicating the score and best-matched sample.

---

## 🔄 Usage Workflow

1. **Setup**  
   - Copy `.env.example` to `.env`, insert your OpenAI API key.
   - Add your JD(s), sample resumes, and candidate resumes (PDF/DOCX) to the corresponding folders.
2. **Run the Notebook**  
   - Open `main_ai_resume.ipynb` and execute all cells.
   - The pipeline processes all files, summarizes, embeds, scores, and selects the best-matching resumes automatically.
3. **Review Output**  
   - Selected resumes are in `selected_resume/YYYY-MM-DD/` with detailed filenames.
   - Log output, matching scores, and all process steps are visible for transparency.

---

## 📝 Output Example

Selected resumes are named as:
[Score]matchedWith[SampleName]_[CandidateName].pdf

yaml
Copy
Edit
*Example:*  
`91_matchedWith_Emily S. Turner_Wei Lin.pdf`  
= Candidate “Wei Lin” best matched sample “Emily S. Turner” (score 91/100).

---

## ✅ Demo Results

Using 5 curated “ideal” sample resumes, the AI pipeline precisely selected 4 out of 5, plus surfaced one high-potential cross-domain candidate—demonstrating both accuracy and practical flexibility.

You can view actual outputs in `selected_resume/YYYY-MM-DD/`.

---

## 🛠️ Requirements & Installation

```
pip install -r requirements.txt
```
Python 3.9+ required.
Key dependencies: openai, sentence-transformers, scikit-learn, numpy, fitz, docx2txt, python-dotenv.


## 🪄 Customization
Thresholds, prompts, and filter logic are easily adjustable in the notebook.

Swap in new job descriptions, sample resumes, or candidate batches with zero code changes.

Designed for HR, talent, and data teams—scalable and explainable.

## 🍂 Notes
All input data is synthetic or AI-edited for privacy and compliance.

Do not upload .env with your real API key; use .env.example for sharing.

For full demo, clone this repo and run main_ai_resume.ipynb in your Jupyter environment.

## 📢 Attribution
This project is open-sourced under the MIT License.
If you use this project (or major portions of it) for commercial purposes or derivative works, please include attribution to the original author.


Xichun Han

LinkedIn: [xichun-han](https://www.linkedin.com/in/xichun-han/)

