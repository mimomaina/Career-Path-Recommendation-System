# Career-Path-Recommendation-System

Overview

The Career Path Recommendation System is an NLP-driven application designed to help job seekers identify their next best job role based on their skills, experience, and qualifications. Using text-based classification, the system predicts suitable job roles, providing insights into career progression and automation risks.

This project is implemented using NLP techniques, machine learning classification models, and Streamlit for an interactive interface.

Problem Statement

Job seekers often struggle with identifying the right career progression based on their expertise. The system addresses this problem by matching users to the most relevant job roles, using NLP to analyze job descriptions, skills, and experience requirements.

Instead of relying on traditional job search filters, this system leverages text similarity and machine learning to make data-driven career recommendations.

Dataset Description

The dataset consists of 292,167 job postings collected between 2021 and 2023. The data is static and was cleaned to focus only on tech-related roles.

Descriptions for each of the columns in the dataset:
1.Job Id: A unique identifier for each job posting.
2.Experience: The required or preferred years of experience for the job.
3.Qualifications: The educational qualifications needed for the job.
4.Salary Range: The range of salaries or compensation offered for the position.
5.Location: The city or area where the job is located.
6.Country: The country where the job is located.
7.Latitude: The latitude coordinate of the job location.
8.Longitude: The longitude coordinate of the job location.
9.Work Type: The type of employment (e.g., full-time, part-time, contract).
10.Company Size: The approximate size or scale of the hiring company.
11.Job Posting Date: The date when the job posting was made public.
12.Preference: Special preferences or requirements for applicants (e.g., Only Male or Only Female, or Both)
13.Contact Person: The name of the contact person or recruiter for the job.
14.Contact: Contact information for job inquiries.
15.Title: The job title or position being advertised.
16.Role: The role or category of the job (e.g., software developer, marketing manager).
17.Job Portal: The platform or website where the job was posted.
18.Job Description: A detailed description of the job responsibilities and requirements.
19.Benefits: Information about benefits offered with the job (e.g., health insurance, retirement plans).
20.Skills: The skills or qualifications required for the job.
21.Responsibilities: Specific responsibilities and duties associated with the job.
22.Company Name: The name of the hiring company.
23.Company Profile: A brief overview of the company's background and mission.
24.Industry(Created Feature):	The sector the job belongs to (e.g., Tech ).
25.Job Automation(Created Feature):	Risk of automation (Low, Semi, High).

Note:

Industry and Job Automation Type were manually created as part of the data cleaning process to add context to job roles.
Some fields (e.g., Contact Info) were dropped due to irrelevance in prediction.

 Exploratory Data Analysis (EDA)






  Model Development
Approach: Text-Based NLP Classification
-We use NLP to classify job roles based on user inputs.

Steps in Model Development:
1. Data Preprocessing:

Text cleaning (lowercasing, removing stopwords, lemmatization).
Tokenization & vectorization using TF-IDF & Word Embeddings (BERT/Sentence Transformers).

2. Feature Engineering:

Convert Skills, Experience, and Responsibilities into vectorized features.
Use TF-IDF for traditional ML models or Transformer embeddings for deep learning.

3. Model Selection & Training:

Classification Model (Random Forest, XGBoost, or BERT) trained to predict the next best job role.
Model evaluates text similarity between user input and job descriptions.

4. Evaluation Metrics:

Accuracy, Precision, Recall, and F1-score for classification.
Cosine Similarity Score for recommendations.

Streamlit Web App Deployment
The user-friendly Streamlit web app allows candidates to input their details and get instant job role recommendations.

User Flow

1. User Inputs:

Skills (e.g., Python, Data Analysis)
Experience (e.g., 3 years)
Qualifications (e.g., Bachelor’s in CS)

2. System Processing:

Cleans and vectorizes input text.
Compares input with job dataset using NLP similarity.
Uses classification model to predict best job match.

3. Output Display:

a. Recommended Job Role(s)
b. Confidence Score for each prediction
c. Industry & Automation Risk Insights

Future Enhancements:

1. Implement personalized job alerts.
2. Improve recommendations using user feedback loops.

