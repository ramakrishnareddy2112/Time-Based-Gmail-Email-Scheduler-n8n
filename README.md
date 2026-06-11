# 📧 Time-Based Gmail Email Scheduler using n8n Low-Code Automation

An automated, low-code email scheduling pipeline built with **n8n**, **Google Sheets**, and **Gmail SMTP**.

Reads recipients from a spreadsheet, filters unsent records, and dispatches emails automatically on a schedule — eliminating repetitive manual work.

---

# 📌 Project Overview

This project implements a fully automated, time-based Gmail email scheduling system using **n8n**, a powerful low-code workflow automation platform.

Instead of manually sending emails one by one, the workflow reads recipient information from Google Sheets, checks whether emails have already been sent, and automatically dispatches personalized Gmail messages only to pending recipients.

The project was developed and tested as part of my **B.Tech CSE (Data Science)** coursework at **Sir Padampat Singhania University, Udaipur**, and is supported by academic documentation.

### Author Information

* **Author:** Pothamsetti Venkata Rama Krishna Reddy
* **Enrollment Number:** 23CS002715
* **Branch:** B.Tech CSE (Data Science)
* **University:** Sir Padampat Singhania University (SPSU), Udaipur

---

# ❗ Problem Statement

Manual email communication faces several challenges:

* Time-consuming and repetitive
* Prone to human errors
* Difficult to scale for large recipient lists
* No proper tracking of sent vs pending emails

Organizations and individuals require an automated solution that can schedule, track, and deliver emails efficiently without developing a custom backend application.

---

# ✅ Solution

A low-code workflow automation system built using n8n that:

1. Reads recipient data from Google Sheets.
2. Checks whether an email has already been sent.
3. Filters pending recipients.
4. Processes recipients one by one.
5. Retrieves email content/templates.
6. Sends Gmail messages automatically.
7. Supports both manual and scheduled execution.

---

# 🏗️ Workflow Architecture

```text
Manual Trigger / Schedule Trigger
               │
               ▼
      Google Sheets (Recipients)
               │
               ▼
        IF Node (Status Check)
               │
               ▼
        Loop Over Items
               │
               ▼
     Google Sheets (Template)
               │
               ▼
          Gmail Send Node
```

---

# ✨ Features

| Feature                    | Description                                           |
| -------------------------- | ----------------------------------------------------- |
| Dynamic Recipient Sourcing | Reads recipient data directly from Google Sheets      |
| Duplicate Send Prevention  | Skips emails already marked as SENT                   |
| Batch Processing           | Processes recipients one at a time                    |
| Flexible Scheduling        | Supports cron-based scheduling                        |
| Secure Authentication      | Uses OAuth2 and encrypted credentials                 |
| Template-Based Emails      | Separates content from recipient data                 |
| Low-Code Architecture      | Built entirely using n8n workflow nodes               |
| Scalable Design            | Can be extended with APIs, databases, and AI services |

---

# 🛠️ Tech Stack

| Technology          | Purpose                      |
| ------------------- | ---------------------------- |
| n8n                 | Workflow Automation          |
| Google Sheets API   | Recipient & Template Storage |
| Gmail SMTP / OAuth2 | Email Delivery               |
| JSON                | Workflow Export Format       |
| Cron Scheduler      | Time-Based Execution         |

---

# 📁 Repository Structure

```text
Time-Based-Gmail-Email-Scheduler-n8n/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── workflow/
│   └── email_scheduler_workflow.json
│
├── documentation/
│   ├── AI_AGENT_DOCUMENTATION_FINAL.pdf
│   └── guide.pdf
│
├── screenshots/
│   ├── workflow-overview.png
│   ├── google-sheet-data.png
│   ├── execution-result.png
│   └── gmail-output.png
│
├── assets/
│   └── architecture-diagram.png
│
└── sample-data/
    └── sample_google_sheet.xlsx
```

---

# ⚙️ Prerequisites

Before running the project:

* n8n Account or Self-Hosted n8n Instance
* Gmail Account
* Google Sheets Access
* Google OAuth Credentials
* Internet Connectivity

---

# 🚀 Installation & Setup

## Step 1: Import Workflow

1. Download the workflow JSON file.
2. Open n8n.
3. Navigate to:

```text
Workflows → Add Workflow → Import from File
```

4. Import `email_scheduler_workflow.json`.

---

## Step 2: Create Google Sheets

### Sheet1 — Recipient Queue

| Name         | Email                                     | Subject          | Send Status |
| ------------ | ----------------------------------------- | ---------------- | ----------- |
| Ravi Kumar   | [ravi@gmail.com](mailto:ravi@gmail.com)   | Project Update   |             |
| Priya Sharma | [priya@gmail.com](mailto:priya@gmail.com) | Meeting Reminder | SENT        |
| Anil Reddy   | [anil@gmail.com](mailto:anil@gmail.com)   | Deadline Alert   |             |

---

### Sheet2 — Email Template

| Template | Body                                                                     |
| -------- | ------------------------------------------------------------------------ |
| Default  | Hi, this is your scheduled notification from the automated email system. |

---

## Step 3: Configure Google Sheets

1. Open Google Sheets Node.
2. Create Google OAuth Credential.
3. Connect your spreadsheet.
4. Select Sheet1 and Sheet2.

---

## Step 4: Configure Gmail

1. Open Gmail Node.
2. Create Gmail OAuth2 Credential.
3. Connect your Gmail account.
4. Configure:

   * To Address
   * Subject
   * Email Body

---

## Step 5: Configure Schedule

Examples:

| Schedule       | Cron           |
| -------------- | -------------- |
| Daily 9 AM     | `0 9 * * *`    |
| Every Hour     | `0 * * * *`    |
| Monday 8 AM    | `0 8 * * 1`    |
| Weekdays 10 AM | `0 10 * * 1-5` |

---

## Step 6: Activate Workflow

1. Execute workflow manually.
2. Verify email delivery.
3. Enable workflow using the **Active** toggle.

---

# 📊 Results

| Test Case                 | Status   |
| ------------------------- | -------- |
| Scheduled Email Delivery  | ✅ Passed |
| Multi-Recipient Support   | ✅ Passed |
| Duplicate Prevention      | ✅ Passed |
| Gmail Integration         | ✅ Passed |
| Google Sheets Integration | ✅ Passed |
| Workflow Execution        | ✅ Passed |

### Key Outcomes

* Reduced manual email handling.
* Improved delivery consistency.
* Eliminated duplicate sends.
* Increased workflow efficiency.

---

# 🔮 Future Improvements

* [ ] Automatically update "SENT" status after successful delivery
* [ ] Slack notifications after email batches complete
* [ ] OpenAI-powered personalized email generation
* [ ] Email open and click tracking
* [ ] CRM integration (HubSpot, Salesforce)
* [ ] Outlook and Yahoo Mail support
* [ ] Analytics Dashboard
* [ ] Web-based scheduling interface

---

# 📚 Documentation

Project documentation is available in:

```text
documentation/
├── AI_AGENT_DOCUMENTATION_FINAL.pdf
└── guide.pdf
```

The documentation covers:

* System Design
* Workflow Architecture
* Implementation Details
* Results
* Future Enhancements

---

# 📸 Screenshots

Add screenshots here after uploading:

### Workflow Overview

![Workflow](screenshots/workflow-overview.png)

### Google Sheets Data

![Google Sheets](screenshots/google-sheet-data.png)

### Workflow Execution

![Execution](screenshots/execution-result.png)

### Email Output

![Email](screenshots/gmail-output.png)

---

# 👤 About Me

**Pothamsetti Venkata Rama Krishna Reddy**

🎓 B.Tech CSE (Data Science)
🏫 Sir Padampat Singhania University, Udaipur

💼 Data Science & AI Intern — DMV CoreTech

🌐 Portfolio: https://ramakrishnareddy.lovable.app

💻 GitHub: https://github.com/ramakrishnareddy2112

📧 Email: [pothamsettiramakrishnareddy@gmail.com](mailto:pothamsettiramakrishnareddy@gmail.com)

---

# 📄 License

This project is licensed under the MIT License.

---

<p align="center">
Built with ❤️ using n8n, Google Sheets, and Gmail Automation
</p>
