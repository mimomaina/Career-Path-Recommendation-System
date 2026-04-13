# Career Path Matching System

## Overview

The Career Path Matching System is a machine learning-driven platform designed to map an individual’s skills to relevant job roles using semantic understanding rather than keyword matching.

The system leverages large-scale job market data and modern natural language processing techniques to:
- Recommend suitable career paths based on existing skills  
- Identify missing skills required for target roles  
- Provide alternative, closely related career options  

Unlike traditional rule-based systems, this approach captures contextual meaning in job descriptions and enables scalable, real-time matching across a large dataset.

---

## Key Highlights

- Built a semantic matching system using **Sentence Transformers (all-MiniLM-L6-v2)**  
- Processed and indexed **~292,000 job profiles**  
- Implemented **FAISS** for efficient large-scale similarity search  
- Used **cosine similarity** for ranking job relevance  
- Applied **MiniBatch K-Means clustering** to group related job families  
- Developed dynamic skill extraction from unstructured job descriptions  
- Designed for **real-time recommendations and scalability**  

---

## Problem Statement

Job seekers often struggle to identify roles that align with their current skill set. Traditional systems rely on:
- Exact keyword matching  
- Static rule-based logic  

These approaches:
- Fail to capture semantic meaning  
- Do not handle variations in terminology  
- Cannot scale effectively across large datasets  
- Ignore relationships between skills and roles  

This project addresses these limitations by using embedding-based similarity and scalable retrieval techniques.

---

## Dataset

- **Source:** Kaggle  
- **Size:** ~292,000 job records  

### Attributes
- Job titles  
- Job descriptions  
- Responsibilities  
- Extracted skills  

### Derived Outputs
- Cleaned job dataset  
- Extracted technical skills (~500 unique skills)  
- Structured skill representations  

---

## Methodology

### 1. Data Preprocessing
- Removed irrelevant fields and duplicates  
- Handled missing values  
- Cleaned text by removing HTML tags and special characters  
- Normalised text (lowercasing, standard formatting)  

---

### 2. Dynamic Skill Extraction
Skills were extracted directly from job descriptions rather than relying on predefined lists.

**Techniques used:**
- Tokenisation  
- Stopword removal  
- N-gram generation (unigrams, bigrams, trigrams)  
- Filtering of generic terms  
- Standardisation of skill variations  

**Outcome:**
- Structured, machine-readable representation of job requirements  
- Improved consistency for downstream modelling  

---

### 3. Embedding Generation (Semantic Representation)

The system uses **Sentence Transformers (SBERT)** to convert job descriptions into dense vector representations.

- Model: `all-MiniLM-L6-v2`  
- Output: 384-dimensional embeddings  

**Why embeddings:**
- Capture contextual meaning beyond keywords  
- Represent semantic similarity between roles  
- Enable comparison of complex text inputs  

---

### 4. Similarity Search with FAISS

To enable fast retrieval across a large dataset, embeddings were indexed using **FAISS (Facebook AI Similarity Search)**.

**Process:**
1. All job embeddings are stored in a FAISS index  
2. User input is converted into an embedding  
3. FAISS retrieves the most similar vectors efficiently  

**Benefits:**
- Scales to hundreds of thousands of records  
- Enables near real-time recommendations  
- Significantly faster than brute-force similarity search  

---

### 5. Cosine Similarity for Ranking

Cosine similarity is used to measure the similarity between user input and job embeddings.

- Values close to **1** → strong match  
- Values near **0** → weak or unrelated  
- Negative values → dissimilar  

This allows ranking of job roles based on relevance.

---

### 6. Clustering with MiniBatch K-Means

To improve exploration and diversity of results, job embeddings were grouped into clusters.

- Algorithm: **MiniBatch K-Means**  
- Reason: Efficient for large datasets  

**Purpose:**
- Identify related job families  
- Improve recommendation diversity  
- Avoid repetitive results  

---

## System Workflow

1. User inputs their skills  
2. Skills are converted into an embedding  
3. FAISS retrieves the most similar job embeddings  
4. Results are ranked using cosine similarity  
5. System:
   - Recommends relevant roles  
   - Identifies missing skills  
   - Suggests related career paths  

---

## Evaluation

### Metric: Cosine Similarity

- **0.8 – 1.0** → Strong match  
- **0.5 – 0.79** → Moderate match  
- **< 0.5** → Weak match  

This metric is used to:
- Rank recommendations  
- Assess relevance of outputs  

---

## User Interface

The system includes an interactive interface built with Streamlit.

**Features:**
- Skill autocomplete  
- Real-time job recommendations  
- Skill gap identification  
- Structured output for user exploration  

---

## Results and Impact

- Successfully mapped user skills to relevant roles across a large dataset  
- Demonstrated scalability using FAISS indexing  
- Improved matching quality compared to keyword-based approaches  
- Enabled identification of alternative career paths beyond exact matches  

---

## Future Improvements

- Integration of additional datasets for broader industry coverage  
- Multi-language support  
- Resume parsing for automated skill extraction  
- Personalised learning recommendations based on skill gaps  
- Deployment as a production-ready API  

---

## Tech Stack

- Python  
- Sentence Transformers (SBERT)  
- FAISS  
- Scikit-learn  
- Pandas  
- NumPy  
- Streamlit  

---

## Installation

```bash
git clone <repository-url>
cd careerpath-matching-system

pip install -r requirements.txt

















  
