# Yardstick_assignment
# 🚀 Groq API Assignment – Conversation Management & Information Extraction

This repository contains my solution for the **Internshala Groq API assignment**.  
I have implemented both required tasks using **Groq API with OpenAI SDK compatibility**, without any external frameworks (only `openai`, `json`, and standard Python).

--------------------------------------------------------------------------------

## 📌 Objectives
1. Task 1 – Conversation Management with Summarization
   - Maintain a running conversation history of user–assistant chats.
   - Summarize conversation history to keep it concise.
   - Truncation options:
     - Limit by number of turns (last n messages).
     - Limit by character/word length.
   - Periodic summarization:
     - Summarize after every k-th run.
     - Replace stored history with summarized version.
   - Demonstration:
     - Multiple conversation samples.
     - Different truncation settings.
     - Summarization after every k-th run.

2. Task 2 – JSON Schema Classification & Information Extraction
   - Create a JSON schema to extract 5 details from chats:
     - Name, Email, Phone, Location, Age
   - Use function calling with Groq API for structured outputs.
   - Demonstration:
     - Parsed at least 3 sample chats.
     - Validated outputs against the schema.

--------------------------------------------------------------------------------

## 🛠️ Tech & Requirements
- Language: Python (Google Colab)
- Libraries:  
  - openai (Groq SDK compatible)  
  - json  
- Models:  
  - Default used: openai/gpt-oss-120b  
  - If unavailable → replace with llama3-8b-8192  

--------------------------------------------------------------------------------

## 📖 How It Works

### 🔹 Task 1 – Conversation Management
- Each user/assistant turn is added to a history list.
- A summarization function uses Groq API to compress the chat.
- History can be truncated by:
  - Last n turns
  - Word count limit
- Every k turns → summarization replaces history.
- Prevents long chats from exceeding context limits.

Example Summarized Output:
[  
  {  
    "role": "system",  
    "content": "Summary of conversation: User greeted the assistant, asked about AI and ML, assistant explained briefly."  
  }  
]

--------------------------------------------------------------------------------

### 🔹 Task 2 – JSON Schema Extraction
Schema Definition:
{  
  "name": "extract_user_info",  
  "parameters": {  
    "type": "object",  
    "properties": {  
      "name": {"type": "string"},  
      "email": {"type": "string"},  
      "phone": {"type": "string"},  
      "location": {"type": "string"},  
      "age": {"type": "string"}  
    },  
    "required": ["name", "email", "phone", "location", "age"]  
  }  
}

Example Input Chat:  
"Hi, I’m Venkat, my email is venkat@example.com, phone 9876543210, I live in Hyderabad, age 21."

Extracted JSON Output:  
{  
  "name": "Venkat",  
  "email": "venkat@example.com",  
  "phone": "9876543210",  
  "location": "Hyderabad",  
  "age": "21"  
}

--------------------------------------------------------------------------------

## ✅ Achievements
- Fully completed both tasks as per requirements.
- Clean, documented Colab notebook.
- No frameworks used.
- Outputs are visible, validated, and ready for evaluation.
- Version tracked on GitHub for submission.

--------------------------------------------------------------------------------

## ⚡ Usage
1. Open `Untitled18.ipynb` in Google Colab.  
2. Set your Groq API key:  
   api_key = "your_groq_api_key"  
3. Run all cells sequentially.  
4. View outputs for both tasks (summarization + schema extraction).  
5. Push notebook to GitHub for evaluation.  

--------------------------------------------------------------------------------

## 🏆 Conclusion
- Task 1 → Implemented conversation history, truncation, periodic summarization.  
- Task 2 → Implemented JSON schema extraction, function calling, validation.  



