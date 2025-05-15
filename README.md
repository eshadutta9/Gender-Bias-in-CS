# Gender Bias in Computer Science Job Advertisements and Job Recommender Systems

This project investigates the presence of gender bias in computer science job advertisements and explores how content-based job recommendation algorithms may perpetuate or mitigate such bias. 

## 📌 Research Objectives

- Analyze how gendered language in job ads has evolved over time.
- Study gender bias variation across country, industry, job role, and work model.
- Evaluate whether job recommendation systems expose male and female applicants to differently gendered jobs.
- Measure the correlation between applicant gender and the genderedness of recommended job ads.

## 🗂️ Repository Structure
### 📁 Scraping Notebooks # Jupyter notebooks for scraping LinkedIn job ads
### 📁 Data Filtering # Cleaning, deduplication, and filtering
### 📁 Annotation # Gender bias annotation using keyword repositories
### 📁 Data Visualization # Exploratory data analysis and visualizations
### 📁 RecSys # Job recommendation models (TF-IDF and Word2Vec)


## ⚙️ Methodology

### 1. Data Collection and Filtering

- **Scraping**: LinkedIn job ads were scraped for alternate years between 2014 and 2024.
- **Filtering**:
  - Duplicates and dummy job ads were removed.
  - Only English-language and computer science-related ads were retained using SOC codes and keyword matching.
  - Metadata like location, industry, and work model were extracted.

### 2. Annotation

- A curated repository of masculine- and feminine-coded words was created from literature.
- High-frequency ambiguous terms (e.g., “lead”, “support”) were removed based on context analysis.
- A sigmoid-based gender bias score was used to label each ad as masculine-coded, feminine-coded, or neutral.

### 3. Synthetic Resume Generation

- Male and female resumes were generated using GPT-based prompts reflecting agentic (male) or communal (female) language, following findings from prior research.

### 4. Recommendation System

- Five content-based recommendation models were built:
  - TF-IDF
  - Word2Vec (CBOW)
  - Word2Vec (Skip-gram)
  - Word2Vec with bigrams (CBOW + Skip-gram)
- Job ads were recommended to resumes based on cosine similarity.

### 5. Fairness Evaluation

- **Disparity-based Exposure** measured how evenly jobs were recommended by gender-coded label.
- **Cramér’s V** was used to assess the strength of association between applicant gender and recommendation bias.


