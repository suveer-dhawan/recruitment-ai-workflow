# 🤖 Recruitment AI Workflow – Hidden Gems Talent x Monash

This project is a complete **AI-powered candidate screening workflow** built using [n8n](https://n8n.io). It was developed during the Monash Teamwork Internship in collaboration with **Hidden Gems Talent** — a recruitment agency based in Singapore/Malaysia — to automate and streamline candidate evaluation.

---

## 🚀 Key Features

✅ **Automated Evaluation Using AI**\
Evaluates candidate responses using OpenAI’s LLM based on specific metrics (e.g. clarity, STAR structure, grammar, impact, ownership).

✅ **Smart Filtering**\
Shortlists candidates with a high-quality score **(≥ 7)** and a low AI-likelihood score **(< 5)**.

✅ **Dynamic Emails**

- **Shortlisted** candidates receive a next-steps email with a Calendly link.
- **Rejected** candidates receive a constructive, personalized feedback email.
- **Internal/CEO** receives a daily summary of top candidates.

✅ **Google Sheets Integration**\
Reads applications and updates evaluation results (score, AI score, rationale, status) directly back to the sheet.

✅ **Fully No-Code / Low-Code**\
Built entirely using n8n’s drag-and-drop automation and JavaScript nodes for clean formatting and custom logic.

---

## 📁 Project Structure

```bash
recruitment-ai-workflow/
├── README.md                   # You're here!
├── FinalWorkflow.json          # Sanitized n8n workflow (no credentials)
├── LLM1.png                    # Candidate Response Evaluation model
├── LLM2.png                    # Tailored Feedback Generating model
├── Overview.png                # Graphical overview of the workflow
```

---

## 📦 Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/suveer-dhawan/recruitment-ai-workflow.git
cd recruitment-ai-workflow
```

### 2. Import the Workflow into n8n

- Open your [n8n instance](https://n8n.io)
- Go to **Workflows > Import**
- Upload `FinalWorkflow.json`

### 3. Add Required Credentials in n8n

You’ll be prompted to link your own:

- ✅ Google Sheets OAuth2
- ✅ OpenAI API Key
- ✅ Gmail / SMTP credentials

These are not included in the workflow file for security.

### 4. Update Placeholders

Make sure to replace:

| Placeholder     | Where               | What to Use                        |
| --------------- | ------------------- | ---------------------------------- |
| `Sheet ID`      | Google Sheets nodes | Your live candidate tracking sheet |
| `Calendly Link` | Shortlist email     | Your real booking link             |
| `CEO email`     | Summary email node  | Correct recipient address          |

---

## ✉️ Example Email Outputs

**Shortlisted Candidate:**

- Subject: *Next Steps – Hidden Gems Application*
- Includes a Calendly link for scheduling an interview

**Rejected Candidate:**

- Subject: *Application Outcome – Hidden Gems*
- Personalized feedback pulled from OpenAI’s rationale field

**CEO Daily Summary:**

- Contains names, scores, summaries, and AI detection scores of shortlisted candidates

---

## 🧐 Evaluation Logic

Each candidate is scored based on:

- Use of the **STAR** method
- Clarity and structure of the response
- Grammar and writing quality
- Level of ownership or problem-solving
- Detection of likely AI-written content

Only candidates with:

- `score >= 7`
- `ai_score < 5`

…are shortlisted.

---

## 🛡️ Security Notes

- ✅ No credentials are stored in the repository.
- ✅ All API and OAuth information must be set up manually in your own n8n instance.
- ✅ You’re safe to clone, import, and deploy.

---

## 🧹 Tools Used

- [n8n](https://n8n.io) – workflow automation platform
- [OpenAI](https://platform.openai.com) – LLM scoring & feedback generation
- [Google Sheets](https://workspace.google.com/products/sheets/) – data source & record keeper
- [Gmail](https://mail.google.com) – email delivery system
- [Calendly](https://calendly.com) – scheduling link integration

---

## 📬 Questions or Support

For any setup help or questions, reach out via GitHub Issues or contact the team lead:

**Suveer Dhawan**\
[suveer.dhawan@nyu.edu](mailto\:suveer.dhawan@nyu.edu)\
[LinkedIn](https://www.linkedin.com/in/suveer-dhawan/)

---

## 📜 License

This project is intended for internal use by Hidden Gems Talent. Contact the author for reuse or deployment rights outside this scope.
