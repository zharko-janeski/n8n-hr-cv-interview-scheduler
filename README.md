# N8N CV-to-Interview Automation

**A 100% automated HR pipeline that reads CVs, screens candidates, requires HR approval, and books interviews.**

![Workflow Architecture](workflow.png)

## How it works
1. Scans a specific folder in Google Drive for PDFs.
2. Uses an AI Agent (Gemini) to extract Candidate Name, Email, and evaluates them for a React Developer role.
3. If the candidate is a fit, it sends an approval email to HR.
4. HR clicks "Approve" or "Reject" in the email.
5. If approved, it automatically creates a calendar appointment.
6. Finally, it sends a confirmation email to the candidate.

## Tech Stack
- **Platform:** n8n (Open-source workflow automation)
- **AI Model:** Google Gemini API
- **Integrations:** Google Drive, Gmail, Google Calendar

## How to Run
1. Clone the repository.
2. Import the `.json` file into your n8n instance.
3. Set up a Google Cloud project and enable the Drive, Gmail, and Calendar APIs.
4. **Connect your Google OAuth2 credentials** for Google Drive, Gmail, and Google Calendar in n8n (Required for file access, email sending, and event creation).
5. **Connect your Google Gemini Chat Model** in the AI Agent node (Used to analyze the CVs).
6. **CRITICAL:** In the Search node, replace the query string `'1nfoIINRfhh-uVhBQcMCbi_ZIsBAiyVe_' in parents` with your own Google Drive Folder ID.
7. Put 3 sample PDF CVs in your Drive folder to test.
