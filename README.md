# Career-Path-Recommendation-System

 __Business Context__
 
Many professionals and job seekers struggle to identify career paths that align with their skills, experience, and academic background. On the employer side, matching candidates to job roles efficiently remains a challenge. This project aims to bridge this gap by developing a machine-learning-based system that recommends suitable career paths to users based on their profiles.

**Goal**

The goal of this project is to build an intelligent career recommendation system that analyzes user profiles and job descriptions to suggest the best job matches. The system leverages Natural Language Processing (NLP) techniques and machine learning classification models to improve job matching accuracy.


**Data Overview**

The dataset consists of the following columns:

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

*Note:*

Industry and Job Automation Type were manually created as part of the data cleaning process to add context to job roles.

Some fields (e.g., Contact Info) were dropped due to irrelevance in prediction.

The 'skills', 'Qualifications' and 'Job Title' columns were preprocessed using standard NLP techniques, including:
-Lowercasing

-Punctuation removal

-Tokenization

-Stopword removal

-Lemmatization


Additionally, Named Entity Recognition (NER) was applied to extract structured information from user profiles and job descriptions.

 
 **Applications**
 
This system can be integrated into:

Job recommendation platforms (e.g., LinkedIn, Indeed, Glassdoor)

Career counseling and guidance systems

Recruitment automation for HR teams

By leveraging NLP and machine learning, the system enhances career decision-making and hiring efficiency.


**Approach to Model Design and Model Integration**

1.Text Preprocessing & Feature Engineering

Applied TF-IDF vectorization to convert text into numerical features.

Used FAISS .

2.**Similary Search Methods**

A. Cosine Similarity (FAISS)

It measures the directional similarity between job vectors, ignoring magnitude.

How
TF-IDF vectors are L2-normalized to make cosine similarity computation equivalent to a dot product.

FAISS indexes these normalized vectors and retrieves the most similar job descriptions based on cosine similarity.

B. L2 (Euclidean Distance) Search

It measures the absolute distance between job vectors in high-dimensional space.

Jobs with smaller Euclidean distances are considered more similar.

FAISS efficiently indexes and retrieves the nearest jobs based on L2 distance.

**Model Evaluation & Insights**

FAISS significantly improved search efficiency compared to traditional methods.

Different distance metrics can be used interchangeably, but cosine similarity worked best for text-based job matching.



**Future Work**

Expand dataset coverage to include more job categories and industries( currently for tech jobs only)



  
