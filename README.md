# ResumeParser
Using NLP to automate resume screening by extracting relevant skills from resumes and matching them with job requirements.

🧠 Resume Screening Tool using Python & NLP
This project is a simple Resume Screening Tool built using Python and Natural Language Processing (NLP). It compares resumes against a given job description to evaluate the suitability of candidates based on skill keyword matching.

🚀 Features
-> Preprocesses text by tokenizing, removing stopwords, and lemmatizing.
-> Extracts relevant skills from resumes.
-> Calculates similarity score between resume skills and job description keywords.
-> Automatically classifies resumes as "Selected" or "Not Selected".
-> Visualizes the selection statistics using a bar chart.
-> Displays results in a clean table using tabulate.

🛠️ Technologies Used
-> Python 3
-> NLTK (Natural Language Toolkit)
-> Pandas
-> Matplotlib
-> Seaborn
-> Tabulate

Execution Process 
📄 1. file.txt – Job Description Input
This file contains the job description or list of required skills written in plain English.

  Example content in file.txt:
  Skills required:
  
  Python
  SQL
  Machine Learning
  Communication

The script reads this file and uses NLP techniques to extract keywords from it, which will act as the reference skills for comparison.

🧠 2. Text Preprocessing
Both the job description and the resumes go through the following preprocessing steps:
Tokenization: Breaking down the text into individual words.
Lowercasing: Converting all words to lowercase for uniformity.
Stopword Removal: Removing common words like "the", "is", "and", etc.
Lemmatization: Reducing words to their root form (e.g., "running" → "run").

This ensures that the comparison is done based on actual meaningful words and not on fluff.

📝 3. Resume Data Input
In the code:

resumes = {
    'resume_id': [1, 2, 3],
    'resume_text': [
        "Experienced in Python and SQL, with a strong background in data analysis and machine learning.",
        "Skilled in communication and teamwork, proficient in SQL and leadership.",
        "Knowledgeable in C++, data structures, and data analysis, with some experience in Python."
        ]
}
The resumes are stored as a dictionary and then converted into a pandas DataFrame.

Each resume is compared against the job keywords extracted from file.txt.

📊 4. Skill Extraction and Scoring
For each resume:
The script extracts relevant skills that match keywords from the job description.
It then calculates a similarity score using this formula:
similarity_score = (Number of matching skills) / (Total number of job keywords)

🎯 5. Resume Evaluation
Based on a threshold (default = 0.4), resumes are marked as:
"Selected" if score ≥ 0.4
"Not Selected" if score < 0.4

These results are stored in the DataFrame and also displayed in a neat table format using the tabulate library.

📈 6. Visualizing Results
A bar chart is generated using seaborn and matplotlib to show how many resumes were selected vs not selected.

✅ Final Output Includes:
Tabular Summary of Resume ID, Skills Found, Similarity Score, and Status.
Bar Chart Visualization of selection results.

