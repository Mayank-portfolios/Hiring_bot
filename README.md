# Hiring_bot
🤖 Hiring Assistant Chatbot

📌 Project Overview The Hiring Assistant Chatbot is a streamlined, AI-powered Streamlit application built using OpenAI's GPT model to simulate a technical recruiter. It gathers candidate information, dynamically generates tailored technical interview questions based on the candidate’s experience and selected tech stack, evaluates answers, and provides an eligibility verdict for the desired role.

🛠 Installation Instructions Prerequisites: Python 3.8+

OpenAI API Key

Virtual Environment (recommended) Set Up Virtual Environment: python -m venv venv .\env\Scripts\activate

#3 Install Dependencies: pip install -r requirements.txt Create a .env File: env Copy Edit OPENAI_API_KEY=your_openai_api_key

#4

Run the App: streamlit run hirechat.py 💡 Usage Guide Fill out your personal and professional details in the form.

Select a tech stack and rate your experience.

The bot generates 4–5 questions tailored to your profile.

Provide your answers.

Click Submit to save your responses.

Click Evaluate my input to get detailed feedback and final eligibility decision.

⚙️ Technical Details 🔧 Libraries Used: streamlit – For interactive pages.

langchain – for managing prompt templates and chaining logic

langchain_openai – integrates LangChain with OpenAI GPT models

python-dotenv – for loading environment variables

🤖 Model: gpt-3.5-turbo via OpenAI API Temperature: 0.1 (stable and deterministic answers)

📐 Architecture: Form UI for data collection (Streamlit) Dynamic prompt generation via ChatPromptTemplate Question generation → Answer collection - Answer store - Answer evaluation - Desicision Making Uses LangChain's invoke() method to execute each stage

✍️ Prompt Design #1 Interview Questions Prompt: You are a Good Technical Recruiter. Make an interview with 4–5 questions on {topic} for a candidate with {experience} years of experience.

#2 Answer Evaluation Prompt: You are a senior technical interviewer. The interview question was: {question} Candidate_answer: {answer} Evaluate the answer and give feedback and state if it is eligible for this Role.

#3

Final Decision Prompt: You are a senior hiring manager reviewing interview results. Here is the interviewer's feedback: {feedback} Based on this, decide if the candidate is eligible for the role and give a final clarification. These prompts are modular and chainable, enabling an interactive flow from question creation to final eligibility decision.

⚔️ Challenges & Solutions Challenge Solution the challenge that i had face is using streamlit with langchain and prompt runing and show output according to run. and the code to retrieve , run , and store data and make desicision according to input.

📁 Directory Structure hiring-assistant-chatbot/ │ ├── hirechat.py # Main application file ├── .env # API key config (not tracked) ├── requirements.txt # Dependencies ├── interview.txt # Stores candidate answers ├── README.md # Project documentation └── .gitignore # Prevents tracking of environment files

🧠 Future Improvements Add resume parsing for automatic input population. Connect to a database for storing applicant data. Support multi-language interview options. Add HR feedback form for collaborative decisions.
