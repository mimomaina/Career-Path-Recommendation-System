# CareerPath Matching System

The **CareerPath Matching System** is a tool designed to help job seekers and career changers explore potential career paths based on their current skills. It matches users' skills to suitable roles, identifies missing skills, and provides actionable insights for career growth.

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [Dataset](#dataset)
4. [Preprocessing Workflow](#preprocessing-workflow)
5. [Skill Extraction Process](#skill-extraction-process)
6. [Autocomplete Functionality](#autocomplete-functionality)
7. [Installation](#installation)
8. [Usage](#usage)
9. [Contributing](#contributing)
10. [License](#license)

---

### Overview
The **CareerPath Matching System** bridges the gap between job seekers' current skills and potential career opportunities. It uses advanced natural language processing (NLP) techniques, including embeddings and clustering, to match skills to roles, identify skill gaps, and provide recommendations for career advancement.

---

### Features
- **Skill-to-Career Matching**: Matches users' skills to relevant job roles.
- **Missing Skill Identification**: Identifies gaps in skills required for desired roles.
- **Dynamic Skill Extraction**: Extracts technical skills from job descriptions for autocomplete functionality.
- **Autocomplete for Skills**: Provides an interactive autocomplete feature for user input.

---

### Dataset
The dataset used in this project includes:
- **Job Titles**: Unique job titles extracted and standardized.
- **Job Descriptions**: Detailed descriptions of roles, responsibilities, and required skills.
- **Skills**: Extracted technical skills from job descriptions.

#### Dataset Files
- `job_descriptions.csv`: Raw job postings with titles, descriptions, and responsibilities.
- `cleaned_job_data.csv`: Preprocessed dataset with extracted skills.
- `extracted_tech_skills.json`: List of unique technical skills extracted from job descriptions.
- `extracted_tech_skills.csv`: CSV version of the extracted skills for easy analysis.

---

### Preprocessing Workflow
1. **Data Cleaning**:
   - Removed irrelevant columns (e.g., `Job Id`).
   - Handled missing values by filling or dropping rows.
   - Standardized date formats and removed duplicates.

2. **Text Preprocessing**:
   - Lowercased text and removed special characters.
   - Tokenized and cleaned job descriptions and skills.

3. **Dynamic Skill Extraction**:
   - Extracted technical skills using regex patterns and NLP techniques.
   - Combined single-word skills, bigrams, and trigrams for multi-word skill recognition.
   - Saved the final skills list as `extracted_tech_skills.json` and `extracted_tech_skills.csv`.

---

### Skill Extraction Process
The skill extraction process involves:
1. **Tokenization**: Splitting job descriptions into individual words and phrases.
2. **Stopword Removal**: Removing common stopwords (e.g., "and," "the").
3. **Multi-Word Skill Recognition**: Combining bigrams and trigrams to capture multi-word skills like "machine learning" or "network security."
4. **Refinement**: Removing overly generic terms (e.g., "problem-solving") while retaining meaningful skills.

---

### Autocomplete Functionality
The system includes an **interactive autocomplete feature** for user input. This feature:
- Uses the extracted technical skills (`extracted_tech_skills.json`) to provide real-time suggestions.
- Enhances user experience by allowing them to quickly select relevant skills.
- Ensures that user inputs are standardized and consistent with the dataset.

Example Implementation:
```python
import json
import streamlit as st

# Load extracted skills
with open("data/extracted_tech_skills.json", "r") as file:
    extracted_skills = json.load(file)

# Autocomplete input for skills
user_skills = st.multiselect(
    "Select your skills (or type to search):",
    options=extracted_skills,
    default=[]
)


### Installation
Clone the repository:
git clone https://github.com/your-username/careerpath-matching-system.git
cd careerpath-matching-system

Install dependencies:

pip install -r requirements.txt

# Download the dataset:

Place job_descriptions.csv and other dataset files in the data/ folder.

# Run the Streamlit app:

streamlit run app.py

#Usage

Launch the app and enter your skills in the input box.
The system will recommend suitable roles and highlight missing skills.
Explore additional filters for refined results.

# Contributing

Contributions are welcome! To contribute:

Fork the repository.

Create a new branch (git checkout -b feature/your-feature).

Commit your changes (git commit -m "Add your feature").

Push to the branch (git push origin feature/your-feature).

Open a pull request.


**License**

This project is licensed under the MIT License. See the LICENSE file for details.

Copy








  
