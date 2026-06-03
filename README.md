# Restaurant AI Customer Support and Booking System

> AI agent trained on a restaurant knowledge base that handles customer inquiries, manages the full reservation lifecycle, and escalates to the team when needed using n8n, OpenAI, PostgreSQL and Airtable.

**Industry:** Food and Beverage / Restaurant Operations
**Built for:** Restaurants that want to automate customer support and reservation management without losing the option for human follow-up.

---

## Demo

[Watch the full walkthrough →](PLACEHOLDER_VIDEO_LINK)

<img width="849" height="399" alt="Github Eves" src="https://github.com/user-attachments/assets/0bcc5436-574b-463d-bf5c-e48dcb639d95" />

---

## The Problem

The restaurant was handling all customer inquiries and reservation requests manually through their website chat. Staff had to respond to every message, look up existing bookings, process changes and cancellations, and log everything by hand. During busy periods, messages went unanswered, bookings were missed, and customers had no reliable way to get a quick response.

---

## The Solution

An AI agent now sits inside the restaurant's chat interface and handles the full support and reservation flow. The agent is trained on the restaurant's own knowledge base, so it answers questions about the menu, hours, location, and policies accurately. It manages reservations end to end: creating new bookings, looking up existing ones, rescheduling, and processing cancellations. Conversation history is stored in PostgreSQL so the agent remembers context across the session. When a customer needs human attention, the system flags it and notifies the team via Slack and Email directly.

---

## How It Works

1. **Customer sends a message** — The customer types a message in the chat window embedded on the restaurant's website. That message fires the workflow instantly via the n8n Chat Trigger running in the background.
2. **AI agent reads and responds from the knowledge base** — An n8n AI Agent node powered by OpenAI processes the message using the restaurant's knowledge base as its source of truth. It answers questions about the menu, opening hours, location, and policies based on real restaurant information, not generic AI responses.
3. **Conversation memory** — PostgreSQL stores the conversation history so the agent maintains context throughout the session and does not ask customers to repeat themselves.
4. **Customer lookup or creation** — The agent checks Airtable for an existing customer record. If none exists, it creates one with the customer's name and contact details.
5. **Reservation management** — Depending on the customer's request, the agent creates a new booking, retrieves an existing one, reschedules it, or processes a cancellation. All changes are written directly to Airtable.
6. **Confirmation sent to customer** — The agent replies with a confirmation of the action taken, including relevant reservation details.
7. **Human escalation when needed** — If the customer requests to speak with someone or the AI cannot resolve the issue, the system notifies the restaurant team via Slack and Email so they can follow up directly.
8. **All records in Airtable** — The team can view every customer and every reservation in a structured Airtable base without touching the chat.

---

## Tech Stack

| Tool | Role |
|---|---|
| **n8n** | Core workflow engine, orchestration, and chat interface host |
| **n8n AI Agent Node** | Runs the LangChain-based agent logic that decides what action to take per message |
| **OpenAI API** | Powers the agent's natural language understanding and response generation |
| **PostgreSQL** | Stores conversation history so the agent maintains context across the session |
| **Airtable** | Database for customer records and reservation entries |
| **Slack** | Receives human escalation alerts when a customer needs team follow-up |
| **Email** | Secondary escalation notification channel for the restaurant team |

---

## Results

- Customer inquiries are answered accurately using the restaurant's own information, not generic AI guesses
- Reservations are created, rescheduled, and cancelled without staff involvement
- Customers can look up their own bookings instantly without calling or waiting for a reply
- Human escalation is automatic, so no request that needs a real person gets dropped
- The agent remembers context within a session, making conversations feel natural rather than repetitive
- Response time dropped from minutes or hours to under 10 seconds for routine inquiries

---

## About

Built by **Charles Emmanuel** — AI & Automation Systems Engineer.
Lagos, Nigeria | [LinkedIn](https://linkedin.com/in/charles-emmanuel-automation) | charlestaylurr@gmail.com

I build systems that remove repetitive manual work so teams can focus on what actually matters. If your business is losing time or money to broken processes, reach out.<img width="849" height="399" alt="Github Eves" src="https://github.com/user-attachments/assets/40ce01b2-7e36-4a95-8b21-deb904640b50" />
<img width="849" height="399" alt="Github Eves" src="https://github.com/user-attachments/assets/957c104c-337d-4057-94a0-52e59945189b" />
