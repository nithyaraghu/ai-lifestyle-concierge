# 🛎️ The AI Lifestyle Concierge
### Google AI Agents Capstone Project

**Submission by:** Nithyashree Raghunathan  
**Model:** Google Gemini 2.0 Flash  
**Tools:** SerpApi (Flights), Spoonacular (Food)

---

## 📖 Project Overview
The **AI Lifestyle Concierge** is a multi-agent system designed to solve the "fragmented app" problem. Instead of switching between travel apps, recipe blogs, and grocery tools, this agent orchestrates them all in a unified interface with persistent memory.

### Key Features
* **🧠 Persistent Memory:** Remembers user identity, diet, and home airport across sessions.
* **✈️ Real-Time Travel:** Fetches live flight prices via Google Flights (SerpApi).
* **🍳 Context-Aware Dining:** Filters recipes based on dietary restrictions stored in memory.
* **🛒 Structured Shopping:** Generates machine-readable JSON shopping lists.

---

## 🏗️ Architecture
The system uses a **Hub-and-Spoke** architecture where Gemini 2.0 acts as the central router.

```mermaid
graph TD
    User(User Input) --> Brain{Gemini 2.0 Flash<br>Router}
    Brain <--> Mem[(Memory Bank<br>User Profile)]
    Brain -- Filters Diet --> Chef[Spoonacular API]
    Brain -- Checks Location --> Travel[SerpApi Flights]
    Brain -- Formats Data --> Shop[JSON Generator]
