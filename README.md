# Unstructured Data Discovery: Topic Modelling Pipeline

## 📌 Project Overview
This project focuses on extracting hidden thematic structures from large-scale, unstructured text datasets. Using the **World Bank Project Documents** dataset, I developed an end-to-end NLP pipeline to automate the categorization of project reports, replacing manual review with a scalable **Latent Dirichlet Allocation (LDA)** model.

## 🛠️ Tech Stack
[![View Notebook](https://img.shields.io/badge/View_Notebook-nbviewer-orange.svg)](https://nbviewer.org/github/KangBin2005/Topic_Modelling/blob/main/244423Q_TopicModelling.ipynb)
![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Gensim](https://img.shields.io/badge/Modeling-Gensim%20%7C%20LDA-red.svg)
![NLP](https://img.shields.io/badge/NLP-NLTK%20%7C%20SpaCy-green.svg)
![Visualization](https://img.shields.io/badge/Viz-PyLDAvis%20%7C%20Seaborn%20%7C%20Matplot-orange.svg)

* **Language:** Python
* **Libraries:** Pandas, NumPy, Regex
* **NLP Tools:** NLTK, Gensim, SpaCy
* **Visualization:** Matplotlib, Seaborn, PyLDAvis

---

## 🔍 Task 1a: Data Preparation & Text Engineering
The foundation of this project involved transforming "noisy" raw text into a machine-readable format optimized for LDA.

### **Preprocessing Workflow:**
* **Noise Reduction:** Stripped HTML tags, non-alphabetic characters, and Unicode noise.
* **Language Filtering:** Retained only English-language documents to ensure semantic consistency.
* **Tokenization & Lemmatization:** Leveraged **NLTK** to remove stopwords and reduce words to their dictionary roots.

---

## 📊 Task 1b: Topic Modelling & Model Selection
In this phase, I implemented the LDA model using the **Gensim** library to discover latent themes across the corpus.

> [!TIP]
> **Interactive Dashboard:** GitHub may struggle to render large interactive notebooks. You can view the full interactive **pyLDAvis** dashboard and evaluation plots via [nbviewer here](https://nbviewer.org/github/KangBin2005/Topic_Modelling/blob/main/244423Q_TopicModelling.ipynb).

### **Model Selection Approach**
To determine the optimal number of topics ($k$), I didn't rely on guesswork. Instead, I executed a data-driven model selection approach:

1.  **Quantitative Metrics:** I calculated **Coherence Scores ($C_v$)** and **Perplexity** across a range of topic numbers.
2.  **Elbow Method:** By plotting these metrics, I identified the point where coherence peaked and perplexity minimized, ensuring the topics were both mathematically distinct and human-interpretable.
3.  **Alpha & Eta Tuning:** Adjusted hyper-parameters to control topic-document and topic-word density for more refined clusters.



### **Visualization & Interpretation**
I utilized **PyLDAvis** to generate an interactive intertopic distance map. This allowed me to:
* View the prevalence of each topic within the entire corpus.
* Analyze the most "salient" terms for each cluster to assign meaningful labels (e.g., *Urban Development, Financial Infrastructure, Environmental Policy*).
* Ensure no significant overlap between clusters, confirming clear thematic boundaries.

---

## 🚀 Key Insights & Impact
* **Automated Categorization:** Developed a system capable of processing thousands of reports, significantly reducing manual effort.
* **Rigor in Evaluation:** Proved model validity through mathematical convergence (Perplexity) and semantic similarity (Coherence).
* **Actionable Intelligence:** Converted 100% unstructured data into structured categories for further trend analysis.

---

## 📂 Project Structure
* `244423Q_DataPreparation.ipynb`: Text cleaning and lemmatization logic.
* `244423Q_TopicModelling.ipynb`: LDA implementation, coherence/perplexity plots, model tuning and **PyLDAvis** dashboard for interactive exploration of topics.

*Note: The processed JSON dataset is excluded due to file size limits but can be regenerated using the provided scripts.*

