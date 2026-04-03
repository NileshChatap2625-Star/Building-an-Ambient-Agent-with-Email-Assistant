📧 Email Assistant using Enron Dataset
🚀 Project Overview

This project is an AI-powered Email Assistant built using Python and Google Colab. It processes email data from the Enron dataset and automatically classifies emails into actionable categories.

The system helps in:

📅 Managing tasks
📤 Forwarding emails
🗂️ Organizing inbox
🤖 Automating decisions
📂 Dataset
Dataset used: Enron Email Dataset
Format: CSV (extracted from ZIP)
Contains:
Sender, Receiver
Subject, Date
Email body
Category labels
⚙️ Technologies Used
Python 🐍
Pandas
Google Colab
Google Drive API
Gmail API
Matplotlib (for visualization)
🔑 Features
✅ 1. Gmail API Integration
Authenticated using Google Colab
Successfully connected to Gmail API
from google.colab import auth
auth.authenticate_user()
✅ 2. Google Drive Integration
Used to store processed dataset
from google.colab import drive
drive.mount('/content/drive')
✅ 3. Data Extraction
Extracted dataset from ZIP file
with zipfile.ZipFile(zip_path, 'r') as zip_ref:
    zip_ref.extractall(extract_path)
✅ 4. Data Processing
Loaded CSV using Pandas
Cleaned and structured data
df = pd.read_csv(csv_path, encoding='latin1')
✅ 5. Email Parsing
Extracted key fields:
Message ID
From
Subject
Date
✅ 6. AI Decision Logic (Agent)
Automatically assigns actions to emails
def agent_action(row):
    if row['Cat_1_level_1'] == 1.0:
        return "Add to calendar / notify team"
    elif row['Cat_2_level_1'] == 1.0:
        return "Forward to accounts department"
    elif row['labeled'] == False:
        return "Mark as personal / no action"
    else:
        return "Archive"
✅ 7. Data Visualization
Pie chart showing action distribution
df['Agent_Action'].value_counts().plot(kind="pie")
📊 Output
Final dataset saved to Google Drive:
/content/drive/MyDrive/email dataset/final email assistant.csv
Includes new column:
Agent_Action
