# Career Recommendation System

## Project Overview
This project is designed to provide **personalized career recommendations** for job seekers in the tech industry. By leveraging **SBERT embeddings with FAISS**, the system will analyze user-inputted skills and match them to relevant job roles based on job descriptions and responsibilities. Unlike traditional keyword-based matching, this approach ensures **context-aware recommendations** that go beyond job titles.

## Features
- **Dynamic Skill Extraction**: Automatically extracts and processes skills from job descriptions.
- **Semantic Job Matching**: Uses **SBERT embeddings** to understand job descriptions contextually.
- **Efficient Search with FAISS**: Enables fast and scalable job recommendations.
- **Autocomplete for User Skills**: Provides suggestions based on extracted skill data.
- **Multiple Distance Metrics**: Compares **Cosine Similarity vs. Euclidean Distance** for better results.

---

## Methodology
### **1 Data Preprocessing & Skill Extraction**
**Extract Job Information**
- Combined **Job Title, Job Description, Responsibilities, and Skills** into a structured format.
- Removed unnecessary columns and cleaned job descriptions (HTML tags, special symbols, etc.).

**Dynamic Skill Extraction**
- **Extracted skills directly from 'skills column'** instead of using a predefined list.
- **Processed multi-word skills** like "machine learning" and "cloud computing."
- **Filtered generic terms** (e.g., "skills", "knowledge") that don't contribute to job matching.
- **Stored extracted skills in JSON and CSV** for future use in autocomplete.

---

### **2 Building the Recommendation Engine**
**Generate SBERT Embeddings**
- Used **`all-MiniLM-L6-v2`** from `sentence-transformers` to encode job descriptions.
- Created embeddings for **both job descriptions and user-inputted skills**.

**Store & Retrieve with FAISS**
- Implemented **HNSW FAISS indexing** for fast similarity search.
- Experimented with **Euclidean Distance vs. Cosine Similarity**.

**Match User Skills to Jobs**
- Transformed user-entered skills into SBERT embeddings.
- Queried FAISS to find the closest job descriptions.
- Returned the **most relevant job title & description**.

**Handling Job Title Variations**
- Prioritized **job descriptions over job titles** for better matching.
- Considered **clustering similar job titles** using DBSCAN or K-Means.

---

## Evaluation Metrics
Since there is no user feedback loop yet, the system was evaluated using offline metrics:

**Top-K Accuracy**: Measures if the correct job title is in the top-K recommendations.
**Cosine Similarity vs. Euclidean Distance**: Compared these metrics to find the best retrieval strategy.
**Manual Sanity Checks**: Random job descriptions were manually validated against retrieved results.

**Goal:** Achieve at least **75% Top-5 accuracy** for strong performance.

---

## Repository Structure
```
Career-Recommendation-System
 ├── data/               # Raw and processed datasets
 ├── models/             # Stored embeddings and FAISS index
 ├── notebooks/          # Jupyter notebooks for experimentation
 ├── (Updated)_Career_recommendation_system.ipynb/            # Python scripts for extraction & preprocessing
 ├── extracted_tech_skills.json  # Extracted skills for autocomplete
 ├── extracted_tech_skills.csv   # Extracted skills in CSV format
 ├── cleaned_job_data.csv        # Preprocessed dataset
 ├── README.md             # Project documentation
```

---

## 🔧 Installation & Usage
### **1 Clone the Repository**
```bash
git clone https://github.com/yourusername/Career-Recommendation-System.git
cd Career-Recommendation-System
```

### **2 Install Dependencies**
```bash
pip install -r requirements.txt
```

### **3 Run Data Preprocessing**
```bash
python scripts/preprocess_data.py
```

### **4 Generate Embeddings & Build FAISS Index**
```bash
python scripts/generate_embeddings.py
```

### **5 Run the Recommendation System**
```bash
python scripts/recommend_job.py --skills "Python, Machine Learning, SQL"
```

---

## Next Steps
**Enhance the recommendation system** by incorporating **real-time user feedback.**  
**Optimize FAISS parameters** for improved accuracy & speed.  
**Deploy as a web API** for broader accessibility.  

---

## License
This project is licensed under the **MIT License**.

---

## Contributing
Pull requests are welcome! If you'd like to contribute, please create an issue first to discuss your proposed changes.

---

## Author
**Your Name**  
Contact: your.email@example.com  
GitHub: [yourusername](https://github.com/yourusername)  

---

**Ready to get started?** Clone the repo and start exploring the power of AI-driven career recommendations!







  
