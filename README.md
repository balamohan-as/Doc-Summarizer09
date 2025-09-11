📄 SmartDoc Summarizer
<p align="center">
<img src="[https://www.google.com/imgres?q=document%20summarizer&imgurl=https%3A%2F%2Fapi.wandb.ai%2Ffiles%2Fmostafaibrahim17%2Fimages%2Fprojects%2F37042936%2Fb9bf06f6.png&imgrefurl=https%3A%2F%2Fwandb.ai%2Fmostafaibrahim17%2Fml-articles%2Freports%2FCompressing-the-Story-The-Magic-of-Text-Summarization--VmlldzozNTYxMjc2&docid=j3cp4TuJCzuXJM&tbnid=0xeYjecZYZDMEM&vet=12ahUKEwjkyMODiNCPAxUDT2wGHVsFDbUQM3oECBoQAA..i&w=532&h=249&hcb=2&ved=2ahUKEwjkyMODiNCPAxUDT2wGHVsFDbUQM3oECBoQAA](https://api.wandb.ai/files/mostafaibrahim17/images/projects/37042936/b9bf06f6.png)" alt="SmartDoc Summarizer Banner">
</p>

SmartDoc Summarizer is an intelligent web application that provides concise summaries of uploaded documents. Built with Python, Streamlit, and Hugging Face Transformers, it allows users to register, log in, and process .pdf, .docx, and .txt files. All generated summaries are securely stored in a Google Firestore database, allowing users to access their history at any time.

🔧 Core Features
• 🤖 AI-Powered Summarization: Utilizes the facebook/bart-large-cnn machine learning model for abstractive text summarization.

• 🔐 Secure User Authentication: Full registration and login functionality powered by Firebase Authentication.

• 💾 Persistent History: Automatically saves every summary to a personal, secure Cloud Firestore database.

• 📄 Multi-Format Support: Natively handles PDF, Microsoft Word, and plain text files.

• 📥 Downloadable Summaries: Users can download any generated summary as a .txt file.

• ✨ Interactive UI: A clean, modern, and user-friendly interface built with Streamlit.

⚙️ Tech Stack
Component

Technology

Frontend

Streamlit

Backend

Python

ML Model

Hugging Face Transformers (BART)

Database

Google Cloud Firestore

Auth

Firebase Authentication

File Parsing

PyPDF2, python-docx

🚀 How to Run This Project Locally
Follow these steps to set up and run the project on your local machine.

Prerequisites
• Python 3.x

• A Google Firebase project

1. Set Up the Firebase Project
Before running the code, you need to configure a Firebase project to handle the backend.

Create a Firebase Project: Go to the Firebase Console and create a new project.

Enable Authentication: In your project, navigate to Build > Authentication, go to the Sign-in method tab, and enable the Email/Password provider.

Create a Firestore Database: Navigate to Build > Firestore Database and click Create database. Start in Test Mode and choose a location.

Get Service Account Key: Go to Project settings > Service accounts and click Generate new private key to download your service account JSON file.

2. Set Up the Local Environment
Clone the Repository:

git clone [https://github.com/Jovalentine/SmartDoc-Summarizer.git](https://github.com/Jovalentine/SmartDoc-Summarizer.git)
cd SmartDoc-Summarizer

Create and Activate a Virtual Environment:

# Create the environment
python -m venv env

# Activate on Windows
env\Scripts\activate

Install Dependencies:

pip install -r requirements.txt

Add Firebase Credentials:

Create a folder named .streamlit in the project root.

Inside it, create a file named secrets.toml.

Paste your Firebase credentials into secrets.toml using the format below:

[firebase]
type = "service_account"
project_id = "your-project-id"
private_key_id = "your-private-key-id"
private_key = "-----BEGIN PRIVATE KEY-----\n ...your-private-key... \n-----END PRIVATE KEY-----\n"
client_email = "your-client-email"
client_id = "your-client-id"
auth_uri = "[https://accounts.google.com/o/oauth2/auth](https://accounts.google.com/o/oauth2/auth)"
token_uri = "[https://oauth2.googleapis.com/token](https://oauth2.googleapis.com/token)"
auth_provider_x509_cert_url = "[https://www.googleapis.com/oauth2/v1/certs](https://www.googleapis.com/oauth2/v1/certs)"
client_x509_cert_url = "your-cert-url"

3. Run the Application
streamlit run app.py

The first time you summarize, the 1.6 GB machine learning model will be downloaded. This is a one-time process.

📂 Project Structure
SmartDoc-Summarizer/
│
├── .streamlit/
│   └── secrets.toml        # Stores Firebase credentials
│
├── app.py                  # Main application script
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation

📈 Future Enhancements
• 🧠 Try Different Models: Experiment with other models like T5 or Pegasus.

• 🔐 Add OAuth: Implement Google or GitHub authentication.

• 📊 Summary Evaluation: Add a feature to visualize summary quality using metrics like ROUGE.

Author
• Bala Mohan A S
