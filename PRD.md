# 📑 Product Requirements Document (PRD)

## 1. Project Overview
- **Summary:**  
  _InBetween Therapy AI is an AI-powered administrative assistant designed to reduce the administrative burden on private therapy practices. The long-term vision includes automating scheduling, client matching, payment follow-ups, and other time-consuming tasks that prevent therapists from focusing on patient care._

## 2. Core Features Implemented
- **Therapist Dashboard:**  
  _Profile section displaying therapist information and weekly statistics (total appointments, hours scheduled, new clients)_
  _Clean, calming sage green design system appropriate for healthcare settings_

- **Scheduling Request Management:**  
  _Display of pending client appointment requests_
  _Toast notifications for user actions to not overwhelm the interface_

- **Weekly Calendar View:**  
  _Visual representation of therapist's weekly schedule_
  _Color-coded appointment blocks for easy scanning_

- **AI Scheduling Assistant (Primary Integration)**  
  _Generates 3 scored time slot recommendations (0-100 fit score)_
  _Provides explanations for each suggestion_
  _Generates client-facing appointment confirmation notes_

## 3. AI Specification
_The AI acts as an experienced practice manager that analyzes multiple factors to recommend optimal appointment times. When a therapist clicks "Suggest Time" on a scheduling request, the AI:_

  - Reviews Client History: Analyzes the client's past appointment patterns (typical days/times, consistency, preferences)
  - Considers Therapist Patterns: Evaluates the therapist's scheduling habits (morning vs. afternoon preference, typical break patterns, etc.) 
  - Assesses Weekly Load: Examines current schedule density to prevent burnout and maintain quality spacing between appointments
  - Evaluates Request Context: Considers the specific nature of the request (new vs. returning client, urgency, flexibility mentioned)

## 4. Technical Architecture
- **Frontend Framework: React + Tailwind CSS**  
  - Component-based architecture
  - Fully responsive across desktop, tablet, and mobile 

- **AI Capabilities:**  
  - Language model analyzes scheduling patterns and generates recommendations
  - Creates natural, human-like explanations for time slot suggestions
  - Drafts professional client confirmation messages
 
- **Frontend Framework: React + Tailwind CSS**  
  - Currently uses mock data for demonstration (no database yet)
  - Hosted on Lovable.app at https://calm-flow-dash.lovable.app/

## 5. Prompting Strategy & Iteration Log
I initially planned to use Google AI Studio for code generation but encountered repeated errors and the preview option would break down. After several failed attempts, I pivoted to Lovable AI.
Prompt 1:
Build a web-based dashboard for therapists to manage appointment requests. The dashboard should show: A therapist profile section with their name and this week's schedule summary. An area displaying incoming scheduling requests from clients, each request should show the client's initials, what date/time they want, whether it's a new or returning client, and buttons to approve or suggest alternatives. A weekly calendar view showing when the therapist already has appointments booked. A clean, calming design appropriate for a mental health practice Make it work on both desktop and mobile screens.
Result:
A therapist dashboard with a calming sage green design system and three key sections. First a therapist profile with weekly stats (appointments, hours, new clients), a pending requests showing client initials, preferred times, new/returning status, and approve/suggest buttons, and a weekly calendar grid displaying all booked appointments. Toast notifications confirm actions without overwhelming the UI.
Rectifications: None

Prompt 2: Create an AI assistant that acts like an experienced therapy practice manager making scheduling recommendations. When deciding what appointment time to suggest, it should consider: The client's past appointment history, the therapist's patterns, and the specific request and how important timing might be. For each suggestion, provide:
A score showing how good of a fit this time slot is
A clear explanation of why this time makes sense
Any concerns to be aware of (like "this client usually comes in the afternoon but requested morning")
The top 3 best options to choose from
The recommendations should help prevent therapist burnout by considering things like adequate breaks and not overloading certain days. Make the explanations sound human and thoughtful, not mechanical.
Result:
An AI scheduling assistant that acts like an experienced practice manager. The functions it performs include:
Reviews client history (past appointments, usual preferences)
Considers therapist patterns (morning/afternoon preference, break needs)
Evaluates weekly load to prevent burnout
Analyzes the specific request context
Recommendations it makes:
Provides 3 scored options (fit score 0-100)
Explains why each time makes sense in thoughtful, human language
Highlights concerns like "client usually prefers afternoons but requested morning"
Color-codes by fit quality (green = excellent, sage = good, amber = acceptable)
Refinement:
Add the name of the website on top (InBetween Therapy AI) and also add a second layer to the "suggest time" functionality, where a note to send to the client is also generated.


## 6. Content Requirements
- **Primaru User Flow:**  
  - Therapist logs into dashboard (simulated - no auth in prototype)
  - Reviews pending appointment requests in left panel
  - Clicks "Suggest Time" on a request requiring scheduling
  - AI modal opens with 3 analyzed recommendations
  - Therapist reads explanations and selects best option
  - Reviews auto-generated client message
  - Clicks "Copy Message" to paste into their communication tool
  - Clicks "Approve" to finalize (demonstrative in prototype)
 

- *Technical Constraints:**  
  - No Real Data Persistence: Refresh clears all state
  - No Authentication: Single-user demonstration only
  - No Calendar Integration: Cannot connect to actual Google Calendar
  - Static Recommendations: AI doesn't actually learn over time yet
    
## 7. Next Steps
- Connect to actual Google Calendar for live availability
- Build backend database to store real appointment data
- Implement functional booking and confirmation workflow
- Add user authentication for therapist login
- Learn from which recommendations therapists actually choose
- Let therapists train the AI on their specific preferences
- Add confidence scores to recommendations
 
