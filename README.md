# AI Receptionist Automation

An AI-powered receptionist built with **n8n** to handle enquiries, route them to the right department, send email confirmations, and maintain enquiry records in Google Sheets.

---

## About the Project

I built this project to explore how AI agents can simplify everyday business communication.

When a company receives enquiries about products, customer support, job opportunities, or general information, each request needs to reach the right team. This workflow automates that process by using an AI receptionist to understand incoming messages and direct them to the appropriate department.

It combines AI agents with email automation and Google Sheets, bringing multiple steps into one connected workflow.

## Key Features

- **AI-powered receptionist** — Processes incoming messages and collects relevant contact information.
- **Smart department routing** — Routes enquiries to Sales, Support, Careers, or General Enquiries.
- **Specialised AI agents** — Uses separate agents for the different enquiry categories.
- **Automated email confirmations** — Sends confirmation emails through Gmail.
- **Google Sheets integration** — Records enquiry details for future reference.
- **Conversation memory** — Uses n8n Simple Memory to support conversational context.

## How It Works

The workflow follows a straightforward process:

1. **Receive:** A user submits an enquiry through the n8n chat interface.
2. **Understand:** The AI receptionist processes the message and collects relevant details.
3. **Classify:** The enquiry is assigned to a department based on its category.
4. **Route:** A Switch node directs the request to the appropriate AI agent.
5. **Confirm:** The configured Gmail node sends an email confirmation.
6. **Record:** Google Sheets stores the configured enquiry information.

### Workflow Overview

```text
                              User Enquiry
                                  |
                                  v
                            AI Receptionist
                                  |
                                  v
                          Department Routing
                                  |
          +------------------+-------------+------------------+
          |                  |             |                  |
          v                  v             v                  v
        Sales              Support       Careers       General Enquiries
          |                  |             |                  |
          +------------------+-------------+------------------+
                                  |
                                  v
                         Email Confirmation
                                  |
                                  v
                          Google Sheets Log
```

*The diagram illustrates the overall process. The actual execution paths depend on the configured n8n nodes.*

## Tech Stack

| Technology | Purpose |
|:--|:--|
| n8n | Workflow automation and orchestration |
| OpenAI API | AI-powered enquiry processing and responses |
| LangChain nodes | AI agent and language model integration |
| Gmail | Automated email confirmations |
| Google Sheets | Enquiry logging |
| Simple Memory | Conversational context |

## Project Structure

```text
ai-receptionist-automation/
│
├── workflow/
│   └── ai_receptionist.json
│
├── screenshots/(screenshots images are attached here)
│
└── README.md
```

The `workflow` directory contains the exported n8n workflow. The `screenshots` directory can be used to store screenshots of the workflow and its execution.

## Getting Started

### Prerequisites

Before running the workflow, you will need:

- An n8n instance, either local or hosted.
- OpenAI API access for the configured model.
- Gmail credentials configured in n8n.
- A Google account and Google Sheets document.

### Setup Instructions

**1. Clone the repository**

```bash
git clone https://github.com/ai-cucu/ai-receptionist-automation.git
cd ai-receptionist-automation
```

**2. Import the workflow**

Open n8n and import `workflow/ai_receptionist.json`.

**3. Configure credentials**

Connect your own OpenAI, Gmail, and Google Sheets credentials. Update the spreadsheet reference, email recipients, and any environment-specific settings.

**4. Review the routing logic**

Check the department categories and ensure the Switch node matches the values produced by the AI receptionist.

**5. Test the workflow**

Submit sample enquiries and verify the department routing, email confirmation, and Google Sheets entry.

## Example Enquiries

| Sample message | Expected department |
|:--|:--|
| I'd like to know more about your products. | Sales |
| I'm facing an issue with an existing order. | Support |
| I'd like to apply for a job. | Careers |
| I have a general question about your company. | General Enquiries |

These examples can be used to test the routing logic. Actual results depend on the AI instructions and workflow configuration.

## Future Improvements

Some improvements I plan to explore:

- [ ] Generate a unique ID for every enquiry.
- [ ] Improve validation of email addresses and phone numbers.
- [ ] Generate PDF summaries of enquiries.
- [ ] Notify the relevant team when a new enquiry arrives through Microsoft Teams or Slack. 

## What I Learned

Working on this project helped me understand how AI agents can be connected to practical business processes. I gained hands-on experience with workflow orchestration, conditional routing, conversational memory, and integrations with external services.

It also highlighted the importance of building a complete process around an AI response — from directing the request to the right department to recording the information for follow-up.

## Author

**Riya Gupta**

AI & Automation | Machine Learning | Workflow Automation

- **GitHub:** [ai-cucu](https://github.com/ai-cucu)
- **LinkedIn:** [Riya Gupta](https://www.linkedin.com/in/riya-gupta-122a2823b/)

---

*An ongoing project exploring practical applications of AI agents and workflow automation.*
