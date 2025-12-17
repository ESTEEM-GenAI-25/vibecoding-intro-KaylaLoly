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
  _Generates 3 scored time slot recommendations (0-100 fit score), with an adjacent calendar view for each option_
  _Provides explanations for each suggestion_
  _Generates client-facing appointment confirmation notes, with a send note button included_

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

For the final submission, I had my co-founder look at my site and give me suggestions on how to ameliorate it. Here is the prompt which was used to make the final touches.
Refining Prompt: Here are some changes I would like to make for the dashboard to be more intuitive and functional:
For suggested times, when someone clicks "suggest time" they shouldn't have to click get "get ai recommendations", the ai should run automatically.
When the ai suggestions appear, show the options both as words and an accompanying visual to make it easier for the therapist to visualize.
For the note to client, instead of "copy note", have a "send note" button.
When suggesting times, address therapist personally “you” not "the therapist"
When an appointment time is selected, it should show up on the calendar and be removed from pending requests.

This final prompt led to the final version of the website now available. At the beginnign of the project, I gave free reign to Lovable AI to see what it would create, and I was okay with the first iterations. But I learned to be more specific with my asks as the website took form, and I had a clearer idea of what worked vs. what did not work.

## 6. UX & Limitations
- *Intended User Journey:**  
  - Therapist logs into dashboard and sees pending appointment requests
  - Reviews client request details (initials, preferred time, appointment type)
  - Clicks "Suggest Time" to get AI recommendations
  - Reviews 3 scored options with explanations and concern flags
  - Selects best option and reviews auto-generated client message
  - Clicks "Send" to send message via their existing communication tool
  - Clicks "Select" to finalize time in their calendar
    
- *Limitations:**  
  - Mock data only: The AI analyzes fake client histories, not real patterns, so recommendations aren't truly personalized yet
  - No authentication: Anyone with the link can access the dashboard - there's no login or user accounts
  - No Calendar Integration: Cannot connect to actual Google Calendar
  - Static Recommendations: AI doesn't actually learn over time yet
 
- *Ethical & Trust-Related Limitations:**  
  - Do not use for real scheduling: This is a demonstration prototype only - it cannot connect to real calendars or send actual client notifications
  - Privacy concerns: In this demo, there's no data encryption or HIPAA compliance measures implemented
  - Cultural/accessibility blind spots: The AI hasn't been trained on diverse scheduling preferences across different cultures, time zones, or accessibility needs
    
## 7. Future Roadmap:
- Real calendar integration: Connect to Google Calendar and other scheduling platforms to read actual availability and book appointments
- Notification system: Automatically send email/SMS confirmations to clients when appointments are scheduled or changed
- Multi-therapist support: Allow practice managers to oversee scheduling across 5-15 therapists with different specialties and availability
 
