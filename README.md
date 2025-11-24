# InBetween Therapy AI

An AI-powered scheduling assistant for therapists that recommends optimal appointment times and generates client messages.

🔗 **[Live Demo](https://calm-flow-dash.lovable.app/)**

---

## What It Does

InBetween Therapy AI helps therapists manage scheduling by:
- Analyzing client patterns and therapist preferences
- Recommending 3 best appointment times with scores (0-100)
- Explaining why each time is a good fit
- Auto-generating professional client messages

---

## How the AI Works

When a therapist clicks **"Suggest Time"**, the AI:

1. **Analyzes patterns:** Reviews client history (typical appointment times, preferences) and therapist habits (morning/afternoon preference, break needs)
2. **Evaluates workload:** Checks current schedule to prevent burnout and ensure adequate spacing
3. **Scores options:** Generates 3 time slots ranked by fit quality (green = excellent, sage = good, amber = acceptable)
4. **Explains reasoning:** Provides human-like explanations like _"This aligns with Sarah's usual afternoon preference and gives you a break after your 12:30 session"_
5. **Drafts message:** Creates a professional confirmation message ready to copy and send

**AI Technology:** Built with Lovable AI platform using large language models for pattern analysis and natural language generation.

---

## Prompt Examples

### Prompt 1: Dashboard Interface
```
Build a web-based dashboard for therapists to manage appointment requests. 
The dashboard should show: A therapist profile section with their name and 
this week's schedule summary. An area displaying incoming scheduling requests 
from clients, each request should show the client's initials, what date/time 
they want, whether it's a new or returning client, and buttons to approve or 
suggest alternatives. A weekly calendar view showing when the therapist already 
has appointments booked. A clean, calming design appropriate for a mental 
health practice. Make it work on both desktop and mobile screens.
```

**Output:** Dashboard with sage green design, therapist profile, pending requests list, weekly calendar, and toast notifications.

---

### Prompt 2: AI Recommendation System
```
Create an AI assistant that acts like an experienced therapy practice manager 
making scheduling recommendations. When deciding what appointment time to 
suggest, it should consider: The client's past appointment history, the 
therapist's patterns, and the specific request and how important timing might 
be. For each suggestion, provide a score showing how good of a fit this time 
slot is, a clear explanation of why this time makes sense, any concerns to be 
aware of, and the top 3 best options to choose from. The recommendations should 
help prevent therapist burnout by considering things like adequate breaks and 
not overloading certain days. Make the explanations sound human and thoughtful, 
not mechanical.
```

**Output:** AI system that analyzes multiple factors and generates 3 scored recommendations with explanations in conversational language.

**Refinement:** Added "InBetween Therapy AI" branding and client message generation feature.

---

## Tech Stack

- **Platform:** Lovable AI
- **Frontend:** React + Tailwind CSS
- **AI:** Large language models for analysis and generation
- **Data:** Mock data (demo prototype)

---

## Current Limitations

- No real data persistence
- No Google Calendar integration yet
- AI uses mock data for demonstration
- Booking workflow is demonstrative only

---

## Next Steps

- Connect to Google Calendar API
- Build backend database
- Add user authentication
- Learn from actual therapist choices

---
