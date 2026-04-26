# AI Powered Talent Scouting and Engagement Agent Built with n8n ( Project Documentation) 

##📌 Problem Statement :
Recruiters spend hours sifting through profiles 
and chasing candidate interest. This AI agent 
automates the entire process!

##🎯 What It Does :
- Takes Job Description as input
- Discovers matching candidates
- Scores candidates on Match Score
- Simulates conversational outreach
- Scores candidate interest level
- Outputs ranked shortlist immediately.

##🔧 Tech Stack:
- n8n (Workflow Automation)
- Google Gemini AI (LLM)
- Google Sheets (Database)
- Postman (API Testing)

##📊 Workflow Blocks:
-> Input :
- Send POST request with Job Description
  to Webhook URL using Postman or any
  API tool in this format:

  POST → http://localhost:5678/webhook/your-id

  Body:
  {
    "jobDescription": "We need a Python 
    developer with 3 years experience 
    in SQL, AWS and Docker. 
    Remote preferred."
  }

  -> Processing :
  1. Webhook - Receives Job Description
             via POST request
  2. JD Parser LLM Chain - Extracts:
   - Role Title
   - Required Skills
   - Experience Years
   - Location
   - Preferred Work Type
  3. Google Sheets - Fetches all 
                   candidate profiles
  4. Loop Over Items - Processes each 
                     candidate one by one
  5. AI Talent Scout - For each candidate:
   - Gives Match Score (0-100)
   - Writes outreach message
   - Simulates candidate reply
   - Gives Interest Score (0-100)
  6. Aggregate - Collects all 
               candidate results
  7. Rank and Combine - Calculates:
     Final Score = (Match × 0.6) + 
                 (Interest × 0.4)
   Sorts candidates highest to lowest
   Assigns rank numbers 1,2,3...
  8. Google Sheets Output - Saves 
                          ranked shortlist
                          to Shortlist tab
  
  -> Output :
  Ranked shortlist in Google Sheets
  with these columns:
  - Rank
  - Candidate Name
  - Email
  - Match Score
  - Interest Score
  - Final Score
  - Interest Level
  - Match Explanation
  - Interest Explanation
  - Outreach Message
  - Candidate Reply

##🚀 How to Use :
1. Import workflow JSON into n8n
2. Configure Google Sheets credentials
3. Configure Gemini API credentials
4. Add candidates to Google Sheet
5. Send POST request with Job Description
6. Check Shortlist tab for results!


  
